## 1. Tắt tính năng tự động sửa lỗi chính tả trên bàn phím bằng Terminal

Tự động sửa lỗi là một trong những tính năng có thể vừa là một công cụ cứu mạng, vừa là một công cụ cực kỳ khó chịu. Có thể bạn sẽ thấy tính năng này hữu ích, tuy nhiên nếu bạn giống mình thấy nó là một tính năng thừa mứa và gây khó chịu cho bạn, bạn có thể tắt tính năng này đi bằng cách mở terminal và gõ dòng lệnh sau:

```markdown
defaults write -g NSAutomaticSpellingCorrectionEnabled -bool false
```

## 2. Sửa lỗi không mở được ứng dụng trên MacOS

Link hướng dẫn: [https://youtu.be/NEspMfcQXdQ](https://youtu.be/NEspMfcQXdQ)

```markdown
xattr -cr 
```

---

## 3. Kiểm tra nhiệt độ, vòng quay quạt và tình trạng pin từ Terminal:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1b180e6c-cc94-4f04-a218-262838737677/Untitled.png)

- **Bước 1: mở Teminal (⌘ + space -> Terminal)**
- **Bước 2: gõ dòng lệnh:**

```markdown
sudo gem install iStats
```

*nếu ai bị lỗi thì thay bằng lệnh**:***

```markdown
 sudo ARCHFLAGS=-Wno-error=unused-command-line-argument-hard-error-in-future gem install iStats
```

*Nếu vẫn tiếp tục lỗi vui lòng nhập 3 lệnh sau:*

```markdown
xcode-select --install
```

```markdown
xcodebuild --license
```

```markdown
sudo ARCHFLAGS=-Wno-error=unused-command-line-argument-hard-error-in-future gem install iStats
```

- **Bước 3: Nhập mật khẩu vào** *(cái này nó không hiện gì cả, nhưng nhập chính xác rồi nhấn enter là được)*
- **Bước 4: gõ lệnh**

```markdown
iStats
```

---

## 4. **Hiển thị file ẩn trên MacOS**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b3a82871-de5d-4a39-8959-e26fb20b6962/Untitled.gif)

File ẩn là những file có màu mờ hơn. Chúng ta nên mở chế độ hiện file ẩn để dễ dàng quản lý file cũng như xoá thư mục một cách triệt để

```markdown
defaults write com.apple.finder AppleShowAllFiles TRUE && killall
```

Để ẩn tất cả các tệp một lần nữa, chạy cùng lệnh trên nhưng thay **TRUE** thành **FALSE:**

- Ngoài ra có thể bấm tổ hợp phím: ⇧**Shift** + ⌘**command** + <•**dấu** **chấm**>

---

## 5. **Cách đổi tên user trong Terminal**

Link hướng dẫn: [https://youtu.be/VbawnISXvr4](https://youtu.be/VbawnISXvr4)

```markdown
export PS1="(tên muốn đặt)(nhớ cách ra)" ; clear;
```

---

## 6. Linh tinh

### 6.1. **Để xem dự báo thời tiết như hình bên dưới:**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/20598e25-8f5e-4de8-8184-9e2cdbdf57b5/Untitled.png)

```markdown
curl wttr.in
```

---

### 6.2. **Xem lịch nhanh:**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/69e4a9fe-0e6b-40b6-a1dd-5071cff22cc4/Untitled.png)

```markdown
cal
```

---

### 6.3. **Mac của tôi đã chạy được bao lâu?**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6c118abe-e337-4d52-a6c6-88c83d3e6e22/Untitled.png)

```markdown
uptime
```

---

## 7. **Đặt màn hình ở chế độ ngủ (sleep) sau thời gian cụ thể:**

```markdown
sudo pmset displaysleep time_in_minutes
```

Giả sử bạn muốn máy Mac của mình ở chế độ ngủ sau 5 phút không hoạt động, lệnh để bật điều này sẽ là:

```markdown
sudo pmset displaysleep 5
```

---

## 8. Xoá cache DNS

Xoá cache DNS sẽ giúp khắc phục một vài vấn đề liên quan đến duyệt web.

```markdown
sudo killall -HUP mDNSResponder;sudo killall mDNSResponderHelper;sudo dscacheutil -flushcache
```

(Sierra trở về sau)

```markdown
sudo killall -HUP mDNSResponder
```

(El Capitan)

Để mở đổ bóng lại: đổi **TRUE** thành **FALSE** rồi enter

## 9. Tắt tự động update MacOS

Tắt thông báo:

```markdown
softwareupdate --schedule off
```

Tắt tự động cập nhật:

```markdown
sudo defaults write /Library/Preferences/com.apple.SoftwareUpdate AutomaticDownload -boolean FALSE
```

## 10. Dock

### 10.1. Để thanh Dock gọn gàng như Window:

Link hướng dẫn: [https://youtu.be/6e6ys84vDTo](https://youtu.be/6e6ys84vDTo)

```markdown
defaults write com.apple.dock static-only -bool TRUE; killall Dock
```

### 10.2.Thêm khoảng trắng trên Dock

Link hướng dẫn: [https://youtu.be/6e6ys84vDTo](https://youtu.be/6e6ys84vDTo)

```markdown
defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'; killall Dock
```

### 10.3.**Làm cho Dock trượt nhanh hơn**

Nếu bạn sử dụng Show and Hide Dock, bạn sẽ nhận thấy rằng khi bạn di chuyển chuột vào Dock đều sẽ có độ trễ. Bạn có thể loại bỏ sự chậm trễ đó bằng các lệnh sau:

```markdown
defaults write com.apple.dock autohide-delay -float 0

killall Dock
```

Số '0' đại diện cho độ trễ trước khi Dock trượt vào chế độ xem, vì vậy nếu bạn muốn giảm nhưng không loại bỏ hoàn toàn, hãy thay thế '0' bằng một giá trị khác, tính bằng giây.

Để hoàn nguyên về mặc định, hãy nhập:

```markdown
defaults delete com.apple.dock autohide-delay

killall Dock
```

Bạn cũng có thể thay đổi tốc độ mà Dock trượt. Để tăng gấp đôi tốc độ, hãy thay thế '0' bằng '0.5' và để giữ nguyên tốc độ, hãy sử dụng '1.'

```markdown
defaults write com.apple.dock autohide-time-modifier -float 0

killall Dock
```

## 11. Auto **Skip Verifying khi mở file DMG trên Mac**

```markdown
defaults write com.apple.frameworks.diskimages skip-verify -bool YES

```

Nếu muốn bật lại thì chạy lệnh sau:

```markdown
defaults write com.apple.frameworks.diskimages skip-verify -bool NO
```

## 12. Máy Mac tự khởi động lại sau sự cố

Trong trường hợp máy bị treo, tránh việc làm mất thời gian chờ đợi thì dòng lệnh này sẽ tự động khởi động lại máy của bạn

```markdown
sudo systemsetup -setrestartfreeze on
```

## 13. Về vấn đề chụp màn hình

### 13.1.Tắt tính năng đổ bóng khi chụp màn hình MacOS

Thông thường khi chụp ảnh màn hình một cửa sổ, ảnh thành phẩm thường được làm thêm một phần nền trắng với hiệu ứng đổ bóng khá đẹp. Tuy nhiên nhiều người không muốn có đổ bóng nên họ sẽ thường phải tắt nó đi bằng cách gõ:

```markdown
defaults write com.apple.screencapture disable-shadow -bool TRUE
killall SystemUIServer
```

### 13.2. Đổi định dạng ảnh chụp màn hình MacOS

Trong trường hợp này thì mình sẽ đổi về định dạng jpg thay vì png cho nó nhẹ nhàng

```markdown
defaults write com.apple.screencapture type jpg
```

### 13.3.**Tạo tên mặc định mới cho ảnh chụp màn hình**

Thông thường, máy Mac viết nó như thế này - *Screen Shot YYYY-DD-MM lúc 20.00.46.png* - và trông nó không được đẹp. Bạn có thể tự tạo tên ảnh theo ý của mình như sau:

```markdown
defaults write com.apple.screencapture name "Tên bạn muốn đặt"
killall SystemUIServer
```

## 14. **Disable Auto-restore in Preview using Terminal on the Mac**

```markdown
defaults write com.apple.Preview NSQuitAlwaysKeepsWindows -bool FALSE
```

Để thay đổi về mặc định, hãy nhập lại lệnh, thay thế FALSE bằng TRUE. Để làm điều tương tự trong QuickTime X, hãy thay thế com.apple.Preview bằng com.apple.QuickTimePlayerX

## 15. Tự động vào BOOT khi khởi động máy

```markdown
sudo nvram manufacturing-enter-picker=true
```

## 16. Tắt cảnh báo khi dọn thùng rác

```markdown
defaults write com.apple.finder WarnOnEmptyTrash -boolean false;
killall Finder
```

## 17. Khắc phục lỗi hao pin

Nhập từng dòng dưới đây, chỗ nào yêu cầu password thì nhập vào:

```markdown
pmset -g
```

```markdown
sudo pmset -a hibernatemode 25
```

```markdown
sudo pmset -a standby 1
```

```markdown
sudo pmset -a standbydelaylow 60
```

```markdown
sudo pmset -a standbydelayhigh 60
```

Để khôi phục trạng thái cũ bạn nhập như sau:

```markdown
sudo pmset -a hibernatemode 3 
```

```markdown
sudo pmset -a standby 1 
```

```markdown
sudo pmset -a standbydelaylow 10800 
```

```markdown
sudo pmset -a standbydelayhigh 8640
```
