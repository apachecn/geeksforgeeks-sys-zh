# 如何在 std::thread 处于睡眠状态时唤醒它？

> 原文:[https://www . geesforgeks . org/a-stdthread 如何在睡眠中唤醒/](https://www.geeksforgeeks.org/how-to-wake-up-a-stdthread-while-it-is-sleeping/)

在这篇文章中，我们将讨论如何在一个 **std::thread** 睡觉的时候唤醒它。众所周知，线程在休眠时是无法退出的。因此，它是使用如下命令唤醒的:

> 标准::条件变量

下面是实现相同的伪代码:

## C++

```
// Custom Class
struct MyClass {

    // Constructor
    MyClass()
        : my_thread([this]() {
            this->thread();
        })
    {
    }

    // Destructor
    ~MyClass()
    {
        {
            std::lock_guard<std::mutex> l(m_);
            stop_ = true;
        }
        c_.notify_one();
        my_thread.join();
    }

    // Function that implements the
    // thread
    void thread()
    {
        while (this->wait_for(std::chrono::minutes(2)))
            SendStatusInfo(some_info);
    }

    // Function to returns false when
    // the thread is stopped
    template <class Duration>
    bool wait_for(Duration duration)
    {
        std::unique_lock<std::mutex> l(m_);
        return !c_.wait_for(l, duration, [this]() {
            return stop_;
        });
    }

    // Conditions Variable
    std::condition_variable c_;
    std::mutex m_;
    bool stop_ = false;
    std::thread my_thread;
};
```