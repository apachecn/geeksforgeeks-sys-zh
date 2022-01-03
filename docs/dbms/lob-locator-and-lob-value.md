# LOB 定位器和 LOB 值

> 原文:[https://www.geeksforgeeks.org/lob-locator-and-lob-value/](https://www.geeksforgeeks.org/lob-locator-and-lob-value/)

有两种方法可用于访问和修改业务线值:

*   使用业务线数据接口
*   Access/modify line of business values using line of business locator

**使用 LOBs 的数据接口**

您可以使用 LOB 的数据接口在 C 应用程序中对 BLOB 和 CLOB 列执行绑定和定义操作。它使您能够在不使用业务线定位器的情况下插入或选择业务线列中的数据如下:

*   Insert character data into CLOB or original data into BLOB with the help of binding variables associated with business line columns.
*   The Define operation is used to define an output buffer in the application to store RAW data selected from BLOB or character data selected from CLOB.

**使用业务线定位器访问/修改业务线值**

存储在数据库中的业务线实例的值可以通过业务线定位器(对业务线值位置的引用)来访问。数据库表只在 CLOB、BLOB、n CLOB 和 BFILE 列中存储定位器。以下是关于业务线定位器和值的要点:

*   To manipulate or access the LOB values, you can pass the LOB locator to various LOB application programming interfaces.
*   The line locator can be easily assigned or reassigned to any line of business instance of the same type.
*   The temporary or persistent characteristics of LOB are independent of locators. Or temporary persistence is only applicable to line of business instances.

**LOB 定位器和 BFILE 定位器**

LOB 类型 CLOB、NCLOB 和 BLOB 的定位器语义与 BFILE 类型的定位器语义之间几乎没有区别:

*   For LOB types CLOB, NCLOB and BLOB, the LOB column stores a locator to the LOB value. Each line of business instance has its own unique copy of line of business value and unique line of business locator.
*   For the initialized BFILE column, this row stores the locator of the external operating system file, which holds the value of BFILE. Each BFILE instance in a given row has its own unique locator; However, two different lines can contain a BFILE locator that points to the same operating system file.

无论业务线的值存储在哪里，定位器都会存储在任何已初始化的业务线列的表行中。每当使用没有识别前缀术语的术语定位器时，它指的是 LOB 定位器和 BFILE 定位器。此外，每当您从表中选择一个业务线时，返回的业务线总是一个临时业务线。有关使用临时 lob 定位器的更多信息，请参见“从 SQL 函数返回的 lob”。

**表 print _ media**Oracle 数据库示例模式 PM 的表`print_media`用作许多示例，定义为:

```
CREATE TABLE print_media
    ( product_id NUMBER(6), 
      ad_id NUMBER(6), 
      ad_composite BLOB, 
      ad_sourcetext CLOB, 
      ad_finaltext CLOB, 
      ad_fltextn NCLOB, 
      ad_textdocs_ntab textdoc_tab, 
      ad_photo BLOB, 
      ad_graphic BFILE, 
      ad_header adheader_typ
    ) 
NESTED TABLE ad_textdocs_ntab STORE AS textdocs_nestedtab;

```