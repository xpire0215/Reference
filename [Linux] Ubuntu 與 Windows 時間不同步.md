# Ubuntu 與 Windows 時間不同步

#### 更新 Ubuntu 時間

```
> sudo apt-get install ntpdate
> sudo ntpdate time.windows.com
```



#### 將時間更新到硬體時間上

```
> sudo hwclock --localtime --systohc
```

