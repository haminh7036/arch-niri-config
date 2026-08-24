# Cấu hình Niri

Cấu hình Niri Wayland Compositor trên Arch Linux cùng **Noctalia Shell**, **Ghostty**, **Hyprlock** và **Fcitx5**.

---

## Cài đặt & Dependencies

### 1. Cài đặt các gói chính thức (Pacman)
```bash
sudo pacman -S niri ghostty hyprlock polkit-gnome playerctl \
  qt6ct adwaita-icon-theme fcitx5 fcitx5-unikey fcitx5-gtk fcitx5-qt \
  xdg-desktop-portal-gnome
```

### 2. Cài đặt các gói từ AUR (Paru)
```bash
paru -S noctalia-shell
```

### 3. Tạo thư mục ảnh chụp màn hình
```bash
mkdir -p ~/Pictures/Screenshots
```

### Thành phần chính
* **Compositor**: `niri`
* **Shell & Launcher (AUR)**: `noctalia-shell`
* **Terminal**: `ghostty`
* **Lock Screen**: `hyprlock`
* **Auth Agent**: `polkit-gnome`
* **Bộ gõ Tiếng Việt**: `fcitx5`, `fcitx5-unikey`
* **Media & Audio**: `playerctl`
* **Theme**: `qt6ct`, `adwaita-icon-theme`

---

## Cài đặt Config

```bash
# Sao lưu cấu hình cũ (nếu có) và clone config
[ -d ~/.config/niri ] && mv ~/.config/niri ~/.config/niri.bak
git clone <URL-REPO-CUA-BAN> ~/.config/niri
```

---

## Phím tắt thông dụng

> `Mod` = Phím `Super` (Windows).

| Phím tắt | Chức năng |
| :--- | :--- |
| `Mod + Space` | Mở App Launcher |
| `Mod + T` | Mở Terminal (Ghostty) |
| `Mod + S` | Control Center (Noctalia) |
| `Mod + V` | Lịch sử Clipboard |
| `Mod + ,` | Cài đặt Noctalia |
| `Mod + Q` | Đóng cửa sổ |
| `Mod + O` | Bật / Tắt Overview |
| `Mod + H / J / K / L` | Di chuyển tiêu điểm (Trái / Dưới / Trên / Phải) |
| `Mod + Ctrl + H / J / K / L` | Di chuyển vị trí cửa sổ / cột |
| `Mod + 1..9` | Chuyển Workspace |
| `Mod + Ctrl + 1..9` | Chuyển cửa sổ sang Workspace |
| `Mod + F` / `Mod + Shift + F` | Phóng to cột / Toàn màn hình |
| `Mod + R` | Đổi độ rộng cột (33% / 50% / 67%) |
| `Mod + B` | Bật / Tắt cửa sổ nổi (Floating) |
| `Mod + W` | Chế độ Tab |
| `Alt + Tab` | Chuyển cửa sổ gần đây |
| `Super + Alt + L` | Khóa màn hình (Hyprlock) |
| `Mod + Shift + /` | Hiện danh sách phím tắt |
| `Mod + Shift + E` | Thoát Niri |
| `Print` / `Ctrl + Print` | Chụp vùng chọn / Toàn màn hình |

---

## Cấu trúc thư mục

* `config.kdl`: File cấu hình chính.
* `noctalia.kdl`: Cấu hình màu sắc (Noctalia tự cập nhật khi đổi theme).
* `config.d/`:
  * `startup.kdl`: Ứng dụng tự chạy và biến môi trường.
  * `input.kdl`: Bàn phím, chuột, touchpad.
  * `layout.kdl`: Gaps, kích thước cột và hiển thị.
  * `rules.kdl`: Luật cửa sổ (Window rules).
  * `binds.kdl`: Phím tắt.

---

## Tùy chỉnh nhanh

* **Đổi phím tắt**: Sửa `config.d/binds.kdl`.
* **Thêm app khởi động**: Thêm `spawn-at-startup "tên-app"` vào `config.d/startup.kdl`.
* **Thêm luật cửa sổ**: Thêm `window-rule` vào `config.d/rules.kdl`.
* **Kiểm tra lỗi cú pháp**:
  ```bash
  niri validate
  ```

---

## License

[MIT](LICENSE)
