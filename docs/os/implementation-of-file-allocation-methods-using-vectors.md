# 使用向量实现文件分配方法

> 原文:[https://www . geeksforgeeks . org/实现文件分配方法使用向量/](https://www.geeksforgeeks.org/implementation-of-file-allocation-methods-using-vectors/)

**前提:** [文件分配方式](https://www.geeksforgeeks.org/file-allocation-methods/)

**不同的文件分配方式:**

**<u>1。连续文件分配方法:</u>**

这是一种分配类型，其中一个文件占用给定内存的[个连续块。这种类型的分配是最快的，因为我们只需将其添加到文件的起始索引中，就可以访问文件的任何部分。但是，当您必须插入一个大小大于最大可用空槽的文件时，这种分配是没有用的。](https://www.geeksforgeeks.org/implementation-of-contiguous-memory-management-techniques/)

下面是**邻接** [**文件分配**](https://www.geeksforgeeks.org/file-allocation-methods/) 的实现，跟随[首适分配](https://www.geeksforgeeks.org/first-fit-allocation-in-operating-systems/):

## C++

```
// C++ implementation of the Contiguous
// File Allocation which follow First-Fit
// algorithm
#include <iostream>
#include <vector>
using namespace std;

// File Class
class File {
public:
    // Name of File
    string filename;

    // Size of file
    size_t size;

    // Partition no. is which part of
    // file is present at a particular
    // block of memory
    int partition;
};
class Block {
    // If Block is occupied
    // by a file or not
    bool occupied = false;

    // File of the block
    File file;

public:
    // This function will set file into
    // current block and set occupied flag
    void set_file(File file)
    {
        this->file = file;
        occupied = true;
    }

    // This function will return
    // filename of given block
    string get_file_name()
    {
        return file.filename;
    }

    // This function will return
    // partition number of file
    int get_file_partition_no()
    {
        return file.partition;
    }

    // This function will return
    // if the block is empty or not
    bool is_empty()
    {
        return !occupied;
    }

    // This function will set the occupied
    // flag as false meaning that it will
    // free the given block
    void set_empty()
    {
        occupied = false;
    }
};

// Function to return the number of
// empty Blocks from given memory
int get_empty_count(vector<Block> memory)
{
    int sum = 0;
    vector<Block>::iterator slot;

    // Count no. of empty blocks in
    // given memory
    for (slot = memory.begin();
         slot != memory.end(); slot++) {
        sum += (*slot).is_empty();
    }

    return sum;
}

// Function will return if the file
// exists in a given memory
bool file_exists(vector<Block> memory,
                 string name)
{
    vector<Block>::iterator slot;

    for (slot = memory.begin();
         slot != memory.end(); slot++) {
        if (!(*slot).is_empty()
            && (*slot).get_file_name() == name) {
            return true;
        }
    }
    return false;
}

// Function will set the file in the memory
// this will follow first fit allocation
void set_contiguous_memory(vector<Block>* memory,
                           vector<int>* index,
                           File file)
{
    bool avail = false;
    int i = 0, count = 0, main_index;
    vector<Block>::iterator slot;

    // Check if the file already exists
    if (file_exists((*memory),
                    file.filename))
        cout << "File already exists"
             << endl;

    else {

        // Iterate through full memory
        for (slot = (*memory).begin();
             slot != (*memory).end(); slot++) {

            // Check if there are
            // contiguous Blocks available
            if ((*slot).is_empty()) {
                count++;

                // This if condition will note
                // the 1st index for each
                // Block empty
                if (count == 1)
                    main_index = i;

                // Check if contiguous
                // Blocks are available,
                // it will set our flag
                // avail as true and break
                if (count == file.size) {
                    avail = true;
                    break;
                }
            }

            // Else if there is even a
            // single non-empty block
            // in between we will set
            // count as 0
            else {
                count = 0;
            }
            i++;
        }

        // If our flag is set,
        // this condition will set
        // our file
        if (avail) {

            // Here starting index of
            // our given file will be
            // pushed in index page
            (*index).push_back(main_index);

            // Utilize count variable
            // again for setting file
            // partition
            count = 0;
            for (int i = main_index;
                 i < main_index + file.size;
                 i++) {
                file.partition = count;
                (*memory).at(i).set_file(file);
                count++;
            }
            cout << "File " << file.filename
                 << " has been successfully"
                 << " allocated"
                 << endl;
        }
        else {
            cout << "The size of the file is"
                 << " greater than"
                 << endl;
            cout << "the greatest slot available"
                 << " in contiguous memory"
                 << endl;
            cout << "Hence, File "
                 << file.filename
                 << " cannot be allocated"
                 << endl;
        }
    }
}

// Function to Delete file from memory
void delete_contiguous_mem(vector<Block>* memory,
                           vector<int>* index_page,
                           string file)
{
    vector<int>::iterator slot;
    int index, i = 0, main_index;

    // Check if the file exist or not
    if (!file_exists((*memory), file))
        cout << "File does not exist" << endl;
    else {

        // Iterate all the indexes
        for (slot = (*index_page).begin();
             slot != (*index_page).end(); slot++) {

            // If specified file is found,
            // this condition will
            // set the value of index no.
            // in index and
            // main_index will have starting
            // location of
            // file in memory
            if ((*memory).at(*slot).get_file_name()
                == file) {
                index = i;
                main_index = (*slot);
                break;
            }
            i++;
        }

        // Iterate through the main index until
        // filename is similar to specified
        // filename and status of Block is
        // not empty
        i = main_index;

        while (i < (*memory).size()
               && (*memory).at(i).get_file_name()
                      == file
               && !(*memory).at(i).is_empty()) {
            // Set the Block as empty
            (*memory).at(i).set_empty();
            i++;
        }

        // Erase entry of file from index page
        (*index_page).erase((*index_page).begin() + index);
        cout << "File " << file
             << " has been successfully deleted"
             << endl;
    }
}

// Function to display main index page
void show_contiguous_index(vector<Block> memory,
                           vector<int> index_page)
{
    int max = 9, i, j;

    // Iterator
    vector<Block>::iterator slot;

    // File Name
    string fname;

    // Iterate through all index pages
    for (i = 0; i < index_page.size();
         i++) {

        if (memory.at(index_page.at(i))
                .get_file_name()
                .length()
            > max) {
            // Get the length of file
            max = memory.at(index_page
                                .at(i))
                      .get_file_name()
                      .length();

            cout << "+" << string(max + 2, '-')
                 << "+---------------+----"
                 << "---------+-----------"
                 << "-------+\n|"
                 << string(max / 2
                               + max % 2 - 4,
                           ' ')
                 << "File Name"
                 << string(max / 2 - 3, ' ')
                 << "| Start Address | "
                 << " End Address | Size"
                 << " of the file |\n+"
                 << string(max + 2, '-')
                 << "+---------------+-------"
                 << "------+------------------+"
                 << endl;
        }
    }

    // Iterate index_pages
    for (i = 0; i < index_page.size();
         i++) {
        cout << "|"
             << string(max / 2 + max % 2
                           - memory
                                     .at(index_page
                                             .at(i))
                                     .get_file_name()
                                     .length()
                                 / 2
                           - memory
                                     .at(index_page
                                             .at(i))
                                     .get_file_name()
                                     .length()
                                 % 2
                           + 1,
                       ' ')
             << memory.at(index_page.at(i))
                    .get_file_name()
             << string(max / 2
                           - memory
                                     .at(index_page
                                             .at(i))
                                     .get_file_name()
                                     .length()
                                 / 2
                           + 1,
                       ' ')
             << "|"
             << string(8
                           - to_string(index_page
                                           .at(i))
                                     .length()
                                 / 2
                           - to_string(index_page
                                           .at(i))
                                     .length()
                                 % 2,
                       ' ')
             << index_page.at(i)
             << string(7
                           - to_string(index_page
                                           .at(i))
                                     .length()
                                 / 2,
                       ' ')
             << "|";
        j = index_page
                .at(i);
        fname = memory
                    .at(j)
                    .get_file_name();

        // Till j is less than memory size
        while (j < memory.size()
               && !memory
                       .at(j)
                       .is_empty()
               && memory
                          .at(j)
                          .get_file_name()
                      == fname) {
            j++;
        }
        j -= 1;

        // Print the index pages details
        cout << string(7
                           - to_string(j)
                                     .length()
                                 / 2
                           - to_string(j)
                                     .length()
                                 % 2,
                       ' ')
             << j
             << string(6
                           - to_string(j)
                                     .length()
                                 / 2,
                       ' ')
             << "|"
             << string(9
                           - to_string(j
                                       - index_page
                                             .at(i)
                                       + 1)
                                     .length()
                                 / 2
                           - to_string(j
                                       - index_page
                                             .at(i)
                                       + 1)
                                     .length()
                                 % 2,
                       ' ')
             << j - index_page.at(i) + 1
             << string(9
                           - to_string(j
                                       - index_page
                                             .at(i)
                                       + 1)
                                     .length()
                                 / 2,
                       ' ')
             << "|"
             << endl;
    }
    cout << "+" << string(max + 2, '-')
         << "+---------------+------"
         << "-------+------------------+"
         << endl;
}

// Function to display index of each
// partition of specified file
void show_contiguous_indexes(vector<Block> memory,
                             vector<int> index_page,
                             string filename)
{
    int index, i;

    // Iterator
    vector<int>::iterator slot;

    // If file exist then display file
    // index and partition
    if (file_exists(memory, filename)) {
        cout << "File Name = " << filename
             << "\n+------------------+----"
             << "--------------+";

        cout << "\n| Current Location |"
             << " Partition Number |";

        cout << "\n+------------------+-"
             << " -----------------+\n";

        // Iterate through all the index
        for (slot = index_page.begin();
             slot != index_page.end(); slot++) {
            if (memory.at(*slot).get_file_name()
                == filename) {
                index = (*slot);
                break;
            }
        }

        // Loop till memory size is greater than
        // index and file is allocated
        // in them
        while (index < memory.size()
               && memory
                          .at(index)
                          .get_file_name()
                      == filename
               && !memory
                       .at(index)
                       .is_empty()) {
            cout << "|"
                 << string(9
                               - to_string(index)
                                         .length()
                                     / 2
                               - to_string(index)
                                         .length()
                                     % 2,
                           ' ')
                 << index
                 << string(9
                               - to_string(index)
                                         .length()
                                     / 2,
                           ' ')
                 << "|"

                 << string(9
                               - to_string(memory
                                               .at(index)
                                               .get
                                                   _file
                                                       _partition
                                                           _no())
                                         .length()
                                     / 2
                               - to_string(memory
                                               .at(index)
                                               .get_file
                                                   _partition
                                                       _no())
                                         .length()
                                     % 2,
                           ' ')

                 << memory
                        .at(index)
                        .get_file_partition_no()

                 << string(9
                               - to_string(memory
                                               .at(index)
                                               .get_file_partition_no())
                                         .length()
                                     / 2,
                           ' ')
                 << "|"
                 << endl;
            index++;
        }
        cout << "+------------------+"
             << "------------------+"
             << endl;
    }
    else
        cout << "File does not exist "
             << "in given memory"
             << endl;
}

// Driver Code
int main()
{
    // Declare memory of size 16 Blocks
    vector<Block> memory(16);

    // Declare index page
    vector<int> index_page;
    File temp;

    cout << "Remaining memory :- "
         << get_empty_count(memory)
         << endl;

    // Set the data
    temp.filename = "home.txt";
    temp.size = 5;
    set_contiguous_memory(&memory,
                          &index_page,
                          temp);

    temp.filename = "Report.docx";
    temp.size = 6;
    set_contiguous_memory(&memory,
                          &index_page,
                          temp);

    temp.filename = "new_img.png";
    temp.size = 3;
    set_contiguous_memory(&memory,
                          &index_page,
                          temp);

    temp.filename = "test.cpp";
    temp.size = 2;
    set_contiguous_memory(&memory,
                          &index_page,
                          temp);

    cout << "Remaining memory :- "
         << get_empty_count(memory)
         << endl;

    // Function call to show all the
    // memory allocation
    show_contiguous_index(memory,
                          index_page);

    cout << "Now we will check each partition of";
    cout << " Report.docx and test.cpp before"
         << endl;

    cout << "deleting them to see"
         << " which locations ";

    cout << "are going to be set free"
         << " as our slots"
         << endl;

    // Function call to show all the
    // memory allocation
    show_contiguous_indexes(memory,
                            index_page,
                            "Report.docx");

    // Function call to show all the
    // memory allocation
    show_contiguous_indexes(memory,
                            index_page,
                            "test.cpp");

    // Now delete Report.docx & test.cpp

    delete_contiguous_mem(&memory,
                          &index_page,
                          "Report.docx");

    delete_contiguous_mem(&memory,
                          &index_page,
                          "test.cpp");

    cout << "Remaining memory :- "
         << get_empty_count(memory)
         << endl;
    // Function call to show all the
    // memory allocation
    show_contiguous_index(memory,
                          index_page);

    // Creating hello.jpeg file now
    // and setting it to memory
    temp.filename = "hello.jpeg";
    temp.size = 8;
    set_contiguous_memory(&memory,
                          &index_page,
                          temp);

    cout << "Check index page: " << endl;

    // Function call to show all the
    // memory allocation
    show_contiguous_index(memory,
                          index_page);
}
```

**Output:** 

```
Remaining memory :- 16
File home.txt has been successfully allocated
File Report.docx has been successfully allocated
File new_img.png has been successfully allocated
File test.cpp has been successfully allocated
Remaining memory :- 0
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       0       |      4      |        5         |
| Report.docx |       5       |      10     |        6         |
| new_img.png |       11      |      13     |        3         |
|   test.cpp  |       14      |      15     |        2         |
+-------------+---------------+-------------+------------------+
Now we will check each partition of Report.docx and test.cpp before
deleting them to see which locations are going to be set free as our slots
File Name = Report.docx
+------------------+------------------+
| Current Location | Partition Number |
+------------------+------------------+
|        5         |        0         |
|        6         |        1         |
|        7         |        2         |
|        8         |        3         |
|        9         |        4         |
|        10        |        5         |
+------------------+------------------+
File Name = test.cpp
+------------------+------------------+
| Current Location | Partition Number |
+------------------+------------------+
|        14        |        0         |
|        15        |        1         |
+------------------+------------------+
File Report.docx has been successfully deleted
File test.cpp has been successfully deleted
Remaining memory:- 8
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       0       |      4      |        5         |
| new_img.png |       11      |      13     |        3         |
+-------------+---------------+-------------+------------------+
The size of the file is greater than
the greatest slot available in contiguous memory
Hence, File hello.jpeg cannot be allocated
Check index page: 
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       0       |      4      |        5         |
| new_img.png |       11      |      13     |        3         |
+-------------+---------------+-------------+------------------+
```

**<u>2。索引文件分配方法</u>** <u>:</u>

这是一种分配类型，其中我们有两个索引页，一个是主索引页，用于所有文件，另一个是子索引页，用于特定文件。这种类型的分配不需要连续的内存槽，因为我们单独跟踪每个块。在下面给定的程序中，向量的向量用于实现主索引和子索引。

以下是**索引文件分配方法**的实现:

## C++

```
// C++ implementation of the Indexed
// File Allocation Method
#include <iostream>
#include <vector>
using namespace std;

// File Class
class File {
public:
    // Name of File
    string filename;

    // Size of file
    size_t size;

    // Partition no. is which part of
    // file is present at a particular
    // block of memory
    int partition;
};

// Block class
class Block {
    // If Block is occupied
    // by a file or not
    bool occupied = false;

    // File of the block
    File file;

public:
    // This function will set file
    // into current block
    // and set occupied flag
    void set_file(File file)
    {
        this->file = file;
        occupied = true;
    }

    // This function will return
    // filename of given block
    string get_file_name()
    {
        return file.filename;
    }

    // This function will return
    // partition number of file
    int get_file_partition_no()
    {
        return file.partition;
    }

    // This function will return
    // if the block is empty or not
    bool is_empty()
    {
        return !occupied;
    }

    // This function will set the
    // occupied flag as false
    // meaning that it will free
    // the given block
    void set_empty()
    {
        occupied = false;
    }
};

// Function to return the number of
// empty Blocks from given memory
int get_empty_count(vector<Block> memory)
{
    int sum = 0;
    vector<Block>::iterator slot;

    // count no. of empty blocks in
    // given memory
    for (slot = memory.begin();
         slot != memory.end(); slot++)
        sum += (*slot).is_empty();
    return sum;
}

// This function will generate random indexes
// from empty memory slots to test indexing
int generate_index(vector<Block> memory)
{
    int index = -1;

    // Check if memory is full
    if (!get_empty_count(memory) == 0) {

        // Here it will generate index until
        // the memory block at generated
        // index is found to be empty
        do {
            index = rand() % memory.size();
            index = abs(index);

        } while (!memory.at(index).is_empty());
    }
    return index;
}

// This function will return if the file
// exists in a given memory
bool file_exists(vector<Block> memory,
                 string name)
{
    vector<Block>::iterator slot;

    for (slot = memory.begin();
         slot != memory.end(); slot++) {
        if (!(*slot).is_empty()
            && (*slot).get_file_name() == name) {
            return true;
        }
    }

    return false;
}

// This function will set file in
// memory and push index for each partition
// and then push the file index to main
// index vector
void set_indexed_memory(vector<Block>* memory,
                        vector<vector<int> >* index_page,
                        File file)
{
    int index;

    // Declaration newpage to set the
    // index page for given file
    vector<int> newpage;

    // Check if file exists
    if (file_exists((*memory), file.filename))
        cout << "File already exists" << endl;
    else {
        // Check if available memory is greater than
        // size of given file
        if (get_empty_count(*memory) >= file.size) {

            // Iterate till file size
            for (int i = 0; i < file.size; i++) {

                // Generate random empty index
                index = generate_index(*memory);

                // Set file partition
                file.partition = i;

                // Push the file to memory
                (*memory).at(index).set_file(file);

                // Push the index to newpage
                newpage.push_back(index);
            }

            // Push new index page into main
            // index page
            (*index_page).push_back(newpage);
            cout << "File " << file.filename
                 << " has been successfully allocated"
                 << endl;
        }
        else {
            cout << "Not enough available space"
                 << endl;
        }
    }
}

// Function to delete a file from given
// indexed memory
void delete_from_indexed_memory(vector<Block>* memory,
                                vector<vector<int> >* index_page,
                                string file)
{
    vector<int>::iterator slot;
    vector<vector<int> >::iterator it;
    int index, i = 0;

    // Check if file exists
    if (file_exists((*memory), file)) {
        // Iterate main index
        for (it = (*index_page).begin();
             it != (*index_page).end(); it++) {
            // Check for sub-index at
            // start location
            slot = (*it).begin();

            // Check if it equals filename
            if ((*memory)
                    .at(*slot)
                    .get_file_name()
                == file) {
                // Set for index and break
                index = i;
                break;
            }
            i++;
        }

        // Set the memory flag as empty
        for (slot = (*index_page).at(index).begin();
             slot != (*index_page).at(index).end();
             slot++)
            (*memory).at(*slot).set_empty();

        // Erase file index from main index page
        (*index_page)
            .erase((*index_page).begin() + index);
        cout << "File " << file
             << " has been successfully deleted"
             << endl;
    }
    else {
        cout << "File does not exist"
             << endl;
    }
}

// Function to display the main index
void show_indexed_index(vector<Block> memory,
                        vector<vector<int> > index_page)
{
    int max = 9;
    vector<Block>::iterator slot;
    vector<vector<int> >::iterator it;

    // Iterate over index pages
    for (it = index_page.begin();
         it != index_page.end(); it++) {
        if (memory
                .at((*it)
                        .at(0))
                .get_file_name()
                .length()
            > max) {
            max = memory
                      .at((*it)
                              .at(0))
                      .get_file_name()
                      .length();
            cout << "+" << string(max + 2, '-')
                 << "+---------------+----------"
                 << "---+------------------+\n|"
                 << string(max / 2 + max % 2 - 4, ' ')
                 << "File Name"
                 << string(max / 2 - 3, ' ')
                 << "| Start Address | End Address"
                 << " | Size of the file |\n+"
                 << string(max + 2, '-')
                 << "+---------------+------"
                 << "-------+------------------+"
                 << endl;
        }
    }

    // Iterate through all the index pages
    for (it = index_page.begin();
         it != index_page.end(); it++) {
        cout << "|"
             << string(max / 2
                           + max % 2
                           - memory
                                     .at((*it)
                                             .at(0))
                                     .get_file_name()
                                     .length()
                                 / 2
                           - memory
                                     .at((*it)
                                             .at(0))
                                     .get_file_name()
                                     .length()
                                 % 2
                           + 1,
                       ' ')
             << memory
                    .at((*it)
                            .at(0))
                    .get_file_name()
             << string(max / 2
                           - memory
                                     .at((*it)
                                             .at(0))
                                     .get_file_name()
                                     .length()
                                 / 2
                           + 1,
                       ' ')
             << "|"
             << string(8
                           - to_string((*it)
                                           .at(0))
                                     .length()
                                 / 2
                           - to_string((*it)
                                           .at(0))
                                     .length()
                                 % 2,
                       ' ')
             << ((*it).at(0))
             << string(7
                           - to_string((*it)
                                           .at(0))
                                     .length()
                                 / 2,
                       ' ')
             << "|"
             << string(7
                           - to_string((*it)
                                           .at((*it)
                                                   .size()
                                               - 1))
                                     .length()
                                 / 2
                           - to_string((*it)
                                           .at((*it)
                                                   .size()
                                               - 1))
                                     .length()
                                 % 2,
                       ' ')
             << (*it)
                    .at((*it).size() - 1)
             << string(6
                           - to_string((*it)
                                           .at((*it)
                                                   .size()
                                               - 1))
                                     .length()
                                 / 2,
                       ' ')
             << "|"
             << string(9
                           - to_string((*it)
                                           .size())
                                     .length()
                                 / 2
                           - to_string((*it)
                                           .size())
                                     .length()
                                 % 2,
                       ' ')
             << (*it).size()
             << string(9
                           - to_string((*it)
                                           .size())
                                     .length()
                                 / 2,
                       ' ')
             << "|" << endl;
        cout << "+" << string(max + 2, '-')
             << "+---------------+----------"
             << "---+------------------+"
             << endl;
    }
}

// Function to show each partition details
// w.r.t filename
void show_indexed_indexes(vector<Block> memory,
                          vector<vector<int> > index_page,
                          string filename)
{
    int index, i = 0, main_index;
    vector<vector<int> >::iterator slot;

    // Check if file exists
    if (file_exists(memory, filename)) {
        for (slot = index_page.begin();
             slot != index_page.end(); slot++) {
            if (memory.at((*slot).at(0)).get_file_name()
                == filename) {
                main_index = i;
                break;
            }
            i++;
        }

        // Display File Details
        cout << "File Name = " << filename << endl;
        cout << "File page index at main index :- "
             << main_index
             << "\n+------------------+------------------+\n";
        cout << "| Current Location | Partition Number |\n";
        cout << "+------------------+------------------+\n";
        for (i = 0;
             i < index_page.at(main_index).size();
             i++) {
            index = index_page
                        .at(main_index)
                        .at(i);
            cout << "|" << string(9
                                      - to_string(index)
                                                .length()
                                            / 2
                                      - to_string(index)
                                                .length()
                                            % 2,
                                  ' ')
                 << index
                 << string(9
                               - to_string(index)
                                         .length()
                                     / 2,
                           ' ')
                 << "|" << string(9
                                      - to_string(memory
                                                      .at(index)
                                                      .get_file_partition_no())
                                                .length()
                                            / 2
                                      - to_string(memory
                                                      .at(index)
                                                      .get_file_partition_no())
                                                .length()
                                            % 2,
                                  ' ')
                 << memory
                        .at(index)
                        .get_file_partition_no()
                 << string(9
                               - to_string(memory
                                               .at(index)
                                               .get_file_partition_no())
                                         .length()
                                     / 2,
                           ' ')
                 << "|" << endl;
        }

        cout << "+------------------+----"
             << "--------------+" << endl;
    }
    else {
        cout << "File does not exist"
             << endl;
    }
}

// Driver Code
int main()
{
    // Declare memory of size 16 Blocks
    vector<Block> memory(16);

    // Declare index page
    vector<vector<int> > index_page;

    File temp;
    cout << "Remaining memory :- "
         << get_empty_count(memory)
         << endl;

    // Set the data
    temp.filename = "home.txt";
    temp.size = 5;
    set_indexed_memory(&memory,
                       &index_page,
                       temp);

    temp.filename = "Report.docx";
    temp.size = 6;
    set_indexed_memory(&memory,
                       &index_page,
                       temp);

    temp.filename = "new_img.png";
    temp.size = 3;
    set_indexed_memory(&memory,
                       &index_page,
                       temp);

    temp.filename = "test.cpp";
    temp.size = 2;
    set_indexed_memory(&memory,
                       &index_page,
                       temp);

    // Print the Remaining memory
    cout << "Remaining memory :- "
         << get_empty_count(memory)
         << endl;

    // Print all the index memory
    show_indexed_index(memory, index_page);
    cout << "Now we will check each partition"
         << " for Report.docx and test.cpp"
         << " before deleting them" << endl;

    // Print all the index memory
    show_indexed_indexes(memory, index_page,
                         "Report.docx");

    // Print all the index memory
    show_indexed_indexes(memory, index_page,
                         "test.cpp");

    // Now delete Report.docx and test.cpp
    delete_from_indexed_memory(&memory,
                               &index_page,
                               "Report.docx");

    delete_from_indexed_memory(&memory,
                               &index_page,
                               "test.cpp");

    cout << "Remaining memory :- "
         << get_empty_count(memory)
         << endl;

    // Print all the index memory
    show_indexed_index(memory, index_page);

    // Creating hello.jpeg file now
    // and setting it to memory
    temp.filename = "hello.jpeg";
    temp.size = 8;

    set_indexed_memory(&memory,
                       &index_page,
                       temp);
    cout << "Check index page :- "
         << endl;

    // Print all the index memory
    show_indexed_index(memory, index_page);

    // Now we will see index for each partition of
    // hello.jpeg
    cout << "Remaining memory :- "
         << get_empty_count(memory)
         << endl;
    cout << "We will check each partition"
         << " for hello.jpeg to see ";
    cout << "if the locations of deleted files"
         << " are utilized or not" << endl;

    // Print all the index memory
    show_indexed_indexes(memory, index_page,
                         "hello.jpeg");
    memory.clear();
    memory.shrink_to_fit();
    index_page.clear();
    index_page.shrink_to_fit();
    return 0;
}
```

**Output:** 

```
Remaining memory :- 16
File home.txt has been successfully allocated
File Report.docx has been successfully allocated
File new_img.png has been successfully allocated
File test.cpp has been successfully allocated
Remaining memory :- 0
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       7       |      1      |        5         |
+-------------+---------------+-------------+------------------+
| Report.docx |       15      |      2      |        6         |
+-------------+---------------+-------------+------------------+
| new_img.png |       4       |      14     |        3         |
+-------------+---------------+-------------+------------------+
|   test.cpp  |       5       |      0      |        2         |
+-------------+---------------+-------------+------------------+
Now we will check each partition for Report.docx and test.cpp before deleting them
File Name = Report.docx
File page index at main index :- 1
+------------------+------------------+
| Current Location | Partition Number |
+------------------+------------------+
|        15        |        0         |
|        10        |        1         |
|        12        |        2         |
|        13        |        3         |
|        11        |        4         |
|        2         |        5         |
+------------------+------------------+
File Name = test.cpp
File page index at main index :- 3
+------------------+------------------+
| Current Location | Partition Number |
+------------------+------------------+
|        5         |        0         |
|        0         |        1         |
+------------------+------------------+
File Report.docx has been successfully deleted
File test.cpp has been successfully deleted
Remaining memory :- 8
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       7       |      1      |        5         |
+-------------+---------------+-------------+------------------+
| new_img.png |       4       |      14     |        3         |
+-------------+---------------+-------------+------------------+
File hello.jpeg has been successfully allocated
Check index page :- 
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       7       |      1      |        5         |
+-------------+---------------+-------------+------------------+
| new_img.png |       4       |      14     |        3         |
+-------------+---------------+-------------+------------------+
|  hello.jpeg |       12      |      13     |        8         |
+-------------+---------------+-------------+------------------+
Remaining memory :- 0
We will check each partition for hello.jpeg to see if the locations of deleted files are utilized or not
File Name = hello.jpeg
File page index at main index :- 2
+------------------+------------------+
| Current Location | Partition Number |
+------------------+------------------+
|        12        |        0         |
|        10        |        1         |
|        11        |        2         |
|        15        |        3         |
|        0         |        4         |
|        2         |        5         |
|        5         |        6         |
|        13        |        7         |
+------------------+------------------+
```

**<u>3。链接文件分配方式</u>** <u>:</u>

这是一种分配方式，我们将一个文件的所有分区链接起来，指向文件下一个分区所在的[内存位置](https://www.geeksforgeeks.org/memory-layout-of-c-program/)。在下面给定的程序中，当到达最后一个分区时，next 将被分配为-1。

以下是**链接文件分配方式**的实现:

## C++

```
// C++ implementation of the Linked
// File Allocation Method
#include <iostream>
#include <vector>
using namespace std;

// File Class
class File {
public:
    // Name of File
    string filename;
    // Size of file
    size_t size;

    // Partition no is which part of
    // file is present at a particular
    // block of memory
    int partition;
};

// Block Class
class Block {
    // If Block is occupied
    // by a file or not
    bool occupied = false;

    // File of the block
    File file;

    // Location of next partition in given memory
    // By default, it is set to -1
    // which indicates there is no next partition
    int next = -1;

public:
    // This will set file into current block
    // and set occupied flag
    void set_file(File file)
    {
        this->file = file;
        occupied = true;
    }

    // This will return filename of given block
    string get_file_name()
    {
        return file.filename;
    }
    // Return partition number of file
    int get_file_partition_no()
    {
        return file.partition;
    }

    // Return if the block is empty or not
    bool is_empty()
    {
        return !occupied;
    }

    // This will set the occupied flag as false
    // meaning that it will free the memory
    void set_empty()
    {
        occupied = false;
    }

    // This function will set location of next
    // partition in given memory
    void set_next(int next)
    {
        this->next = next;
    }

    // This function will return location
    // of next partition
    int get_next()
    {
        return next;
    }
};

// Function to return the number of
// empty Blocks from given memory
int get_empty_count(vector<Block> memory)
{
    int sum = 0;
    vector<Block>::iterator slot;

    // Count no. of empty blocks in given memory
    for (slot = memory.begin();
         slot != memory.end(); slot++)
        sum += (*slot).is_empty();

    // Return the empty count
    return sum;
}

// Function to generate random indexes
// from empty memory slots to test indexing
int generate_index(vector<Block> memory)
{
    int index = -1;

    // Check if memory is full
    if (!get_empty_count(memory) == 0) {
        // Here it will generate index until
        // the memory block at generated
        // index is found to be empty
        do {
            index = rand() % memory.size();
            index = abs(index);
        } while (!memory.at(index).is_empty());
    }
    return index;
}

// This function will return if the file
// exists in a given memory
bool file_exists(vector<Block> memory,
                 string name)
{
    vector<Block>::iterator slot;

    for (slot = memory.begin();
         slot != memory.end(); slot++)
        if (!(*slot).is_empty()
            && (*slot).get_file_name()
                   == name)
            return true;

    return false;
}

// This function will set the file in memory
void set_linked_memory(vector<Block>* memory,
                       vector<int>* index_page,
                       File file)
{
    int index = -1, prev = -1, i = 0;

    // Check if file exists already
    if (!file_exists((*memory), file.filename)) {

        // Check if memory is available
        // according to file size
        if (get_empty_count(*memory) >= file.size) {

            // Generate empty index
            index = generate_index(*memory);

            // Push 1st index to index page
            (*index_page).push_back(index);
            for (i = 0; i < file.size - 1; i++) {
                // Set partition
                file.partition = i;

                // Set file into memory
                (*memory).at(index).set_file(file);

                // Note down prev index before
                // generating next index
                prev = index;

                // Generate empty index
                index = generate_index(*memory);

                // Set the next location to generated
                // index in previous index
                (*memory).at(prev).set_next(index);
            }

            // Set last partition and file
            file.partition = file.size - 1;
            (*memory).at(index).set_file(file);

            cout << "File " << file.filename
                 << " has been successfully allocated"
                 << endl;
        }
        else
            cout << "Not enough available memory"
                 << endl;
    }
    else
        cout << "File already exists in given memory"
             << endl;
}

// Function will delete the file from
// memory specified by name
void delete_from_linked_memory(vector<Block>* memory,
                               vector<int>* index_page,
                               string file)
{
    int index, next, previous, main_index, i = 0;
    vector<int>::iterator slot;

    // Check if file exists
    if (file_exists((*memory), file)) {

        // Iterate through the index page
        // to find 1st partition
        for (slot = (*index_page).begin();
             slot != (*index_page).end();
             slot++) {

            // Check if file stored at index has
            // the same name we wish to delete
            if ((*memory)
                    .at(*slot)
                    .get_file_name()
                == file) {
                // Main index is w.r.t memory location
                main_index = (*slot);

                // index is w.r.t index page
                // entry location
                index = i;
                break;
            }
            i++;
        }

        // 1st partition
        i = main_index;

        // Check while next location comes as -1
        while (i != -1
               && (*memory)
                          .at(i)
                          .get_file_name()
                      == file) {

            // set the Block free
            (*memory).at(i).set_empty();

            // Note the location into previous
            previous = i;

            // get the next location
            i = (*memory).at(i).get_next();

            // set -1 as next location into
            // previous location
            (*memory).at(previous).set_next(-1);
        }

        // Erase the entry of file from index
        // page as well
        (*index_page)
            .erase((*index_page)
                       .begin()
                   + index);
        cout << "File " << file
             << " has been successfully deleted"
             << endl;
    }
    else {
        cout << "File does not exist in given memory"
             << endl;
    }
}

// Function to display main index page
void show_linked_index(vector<Block> memory,
                       vector<int> index)
{
    int max = 9, i, count;

    // Iterator
    vector<int>::iterator slot;

    // File Name
    string fname;

    // Iterate through all index pages
    for (slot = index.begin();
         slot != index.end(); slot++) {

        if (memory
                .at(*slot)
                .get_file_name()
                .length()
            > max) {
            max = memory
                      .at(*slot)
                      .get_file_name()
                      .length();
            cout << "+" << string(max + 2, '-')
                 << "+---------------+---------"
                 << "----+------------------+";
            cout << "\n|"
                 << string(max / 2 + max % 2 - 4,
                           ' ')
                 << "File Name"
                 << string(max / 2 - 3, ' ');
            cout << "| Start Address | End Address"
                 << " | Size of the file |\n+"
                 << string(max + 2, '-');
            cout << "+---------------+--------"
                 << "-----+------------------+"
                 << endl;
        }
    }

    // Iterate through index
    for (slot = index.begin();
         slot != index.end();
         slot++) {

        i = (*slot);
        fname = memory
                    .at(i)
                    .get_file_name();
        count = 1;
        while (memory.at(i).get_next() != -1
               && memory
                          .at(i)
                          .get_file_name()
                      == fname) {
            i = memory.at(i).get_next();
            count++;
        }

        cout << "|" << string(max / 2 + max % 2
                                  - memory
                                            .at(*slot)
                                            .get_file_name()
                                            .length()
                                        / 2
                                  - memory
                                            .at(*slot)
                                            .get_file_name()
                                            .length()
                                        % 2
                                  + 1,
                              ' ')
             << memory
                    .at(*slot)
                    .get_file_name()
             << string(max / 2 - memory.at(*slot).get_file_name().length() / 2 + 1,
                       ' ')
             << "|"
             << string(8
                           - to_string(*slot)
                                     .length()
                                 / 2
                           - to_string(*slot)
                                     .length()
                                 % 2,
                       ' ')
             << (*slot)
             << string(7
                           - to_string(*slot)
                                     .length()
                                 / 2,
                       ' ')
             << "|"
             << string(7
                           - to_string(i)
                                     .length()
                                 / 2
                           - to_string(i)
                                     .length()
                                 % 2,
                       ' ')
             << i
             << string(6
                           - to_string(i)
                                     .length()
                                 / 2,
                       ' ')
             << "|"
             << string(9
                           - to_string(count)
                                     .length()
                                 / 2
                           - to_string(count)
                                     .length()
                                 % 2,
                       ' ')
             << count
             << string(9
                           - to_string(count)
                                     .length()
                                 / 2,
                       ' ')
             << "|" << endl;
    }

    cout << "+" << string(max + 2, '-')
         << "+---------------+----------"
         << "---+------------------+"
         << endl;
}

// Function to check all the partitions of file
// w.r.t filename specified
void show_linked_indexes(vector<Block> memory, vector<int> index_page,
                         string filename)
{
    int index;
    vector<int>::iterator slot;

    // If file exists
    if (file_exists(memory, filename)) {
        cout << "File Name = " << filename;
        cout << "\n+------------------+----------"
             << "--------+------------------+";
        cout << "\n| Current Location |Next part"
             << " Location| Partition Number |";
        cout << "\n+------------------+----------"
             << "--------+------------------+\n";

        // Iterate through all index
        for (slot = index_page.begin();
             slot != index_page.end(); slot++) {
            if (memory
                    .at(*slot)
                    .get_file_name()
                == filename) {
                index = (*slot);
                break;
            }
        }

        // Loop till index is not -1
        while (index != -1) {
            cout << "|"
                 << string(9
                               - to_string(index)
                                         .length()
                                     / 2
                               - to_string(index)
                                         .length()
                                     % 2,
                           ' ')
                 << index
                 << string(9
                               - to_string(index)
                                         .length()
                                     / 2,
                           ' ')
                 << "|"
                 << string(9
                               - to_string(memory
                                               .at(index)
                                               .get_next())
                                         .length()
                                     / 2
                               - to_string(memory
                                               .at(index)
                                               .get_next())
                                         .length()
                                     % 2,
                           ' ')
                 << memory
                        .at(index)
                        .get_next()
                 << string(9
                               - to_string(memory
                                               .at(index)
                                               .get_next())
                                         .length()
                                     / 2,
                           ' ')
                 << "|"
                 << string(9
                               - to_string(memory
                                               .at(index)
                                               .get_file_partition_no())
                                         .length()
                                     / 2
                               - to_string(memory
                                               .at(index)
                                               .get_file_partition_no())
                                         .length()
                                     % 2,
                           ' ')
                 << memory
                        .at(index)
                        .get_file_partition_no()
                 << string(9
                               - to_string(memory
                                               .at(index)
                                               .get_file_partition_no())
                                         .length()
                                     / 2,
                           ' ')
                 << "|" << endl;
            index = memory
                        .at(index)
                        .get_next();
        }

        cout << "+------------------+---------"
             << "---------+------------------+"
             << endl;
    }
    else {
        cout << "Given file does not exist"
             << " in given memory"
             << endl;
    }
}

// Driver Code
int main()
{

    // Declare memory of size 16 Blocks
    vector<Block> memory(16);

    // Declare index page
    vector<int> index_page;
    File temp;
    cout << "Remaining memory :- "
         << get_empty_count(memory) << endl;

    // Set the data
    temp.filename = "home.txt";
    temp.size = 5;
    set_linked_memory(&memory,
                      &index_page,
                      temp);

    temp.filename = "Report.docx";
    temp.size = 6;
    set_linked_memory(&memory,
                      &index_page,
                      temp);

    temp.filename = "new_img.png";
    temp.size = 3;
    set_linked_memory(&memory,
                      &index_page,
                      temp);

    temp.filename = "test.cpp";
    temp.size = 2;
    set_linked_memory(&memory,
                      &index_page
                          temp);

    cout << "Files have been successfully set"
         << endl;
    cout << "Remaining memory :- "
         << get_empty_count(memory) << endl;

    // Print all the linked index
    show_linked_index(memory, index_page);
    cout << "Now we will check index"
         << " of each partition of ";
    cout << "Report.docx and test.cpp"
         << " before deleting them"
         << endl;

    // Print all the linked index
    show_linked_indexes(memory, index_page,
                        "Report.docx");

    // Print all the linked index
    show_linked_indexes(memory, index_page,
                        "test.cpp");

    // Now delete Report.docx and test.cpp
    delete_from_linked_memory(&memory,
                              &index_page,
                              "Report.docx");
    delete_from_linked_memory(&memory,
                              &index_page,
                              "test.cpp");
    cout << "Remaining memory :- "
         << get_empty_count(memory) << endl;

    // Print all the linked index
    show_linked_index(memory, index_page);

    // Creating hello.jpeg file now
    // and setting it to memory
    temp.filename = "hello.jpeg";
    temp.size = 8;

    // Set Linked memory
    set_linked_memory(&memory,
                      &index_page,
                      temp);
    cout << "Check index page :- "
         << endl;

    // Print all the linked index
    show_linked_index(memory, index_page);

    // Now we will see index for each partition
    // of hello.jpeg
    cout << "Remaining memory :- "
         << get_empty_count(memory) << endl;
    cout << "We will check each partition for"
         << " hello.jpeg ";
    cout << "to see if deleted locations are"
         << " utilized or not"
         << endl;

    // Print all the linked index
    show_linked_indexes(memory,
                        index_page,
                        "hello.jpeg");
    memory.clear();
    memory.shrink_to_fit();
    index_page.clear();
    index_page.shrink_to_fit();

    return 0;
}
```

**Output:** 

```
Remaining memory :- 16
File home.txt has been successfully allocated
File Report.docx has been successfully allocated
File new_img.png has been successfully allocated
File test.cpp has been successfully allocated
Files have been successfully set
Remaining memory :- 0
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       7       |      1      |        5         |
| Report.docx |       15      |      2      |        6         |
| new_img.png |       4       |      14     |        3         |
|   test.cpp  |       5       |      0      |        2         |
+-------------+---------------+-------------+------------------+
Now we will check index of each partition of Report.docx and test.cpp before deleting them
File Name = Report.docx
+------------------+------------------+------------------+
| Current Location |Next part Location| Partition Number |
+------------------+------------------+------------------+
|        15        |        10        |        0         |
|        10        |        12        |        1         |
|        12        |        13        |        2         |
|        13        |        11        |        3         |
|        11        |        2         |        4         |
|        2         |        -1        |        5         |
+------------------+------------------+------------------+
File Name = test.cpp
+------------------+------------------+------------------+
| Current Location |Next part Location| Partition Number |
+------------------+------------------+------------------+
|        5         |        0         |        0         |
|        0         |        -1        |        1         |
+------------------+------------------+------------------+
File Report.docx has been successfully deleted
File test.cpp has been successfully deleted
Remaining memory :- 8
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       7       |      1      |        5         |
| new_img.png |       4       |      14     |        3         |
+-------------+---------------+-------------+------------------+
File hello.jpeg has been successfully allocated
Check index page :- 
+-------------+---------------+-------------+------------------+
|  File Name  | Start Address | End Address | Size of the file |
+-------------+---------------+-------------+------------------+
|   home.txt  |       7       |      1      |        5         |
| new_img.png |       4       |      14     |        3         |
|  hello.jpeg |       12      |      13     |        8         |
+-------------+---------------+-------------+------------------+
Remaining memory :- 0
We will check each partition for hello.jpeg to see if deleted locations are utilized or not
File Name = hello.jpeg
+------------------+------------------+------------------+
| Current Location |Next part Location| Partition Number |
+------------------+------------------+------------------+
|        12        |        10        |        0         |
|        10        |        11        |        1         |
|        11        |        15        |        2         |
|        15        |        0         |        3         |
|        0         |        2         |        4         |
|        2         |        5         |        5         |
|        5         |        13        |        6         |
|        13        |        -1        |        7         |
+------------------+------------------+------------------+
```