# Hello World (Rust Project)

This is a simple "Hello, World!" application written in Rust. This guide will help you build and install it on Arch Linux using AUR (Arch User Repository) helper tools.

## Prerequisites

Before you begin, you'll need to have `rustup` (the Rust toolchain installer) and an AUR helper like `yay` installed.

1.  **Install `rustup`**:
    ```bash
    yay -S rustup
    ```
    Then initialize rustup:
    ```bash
    rustup default nightly
    ```

## Installation Methods for This Project

You can build and install this `hello-world` project as either a binary package or a source package. Building from source is generally recommended for AUR packages.

### 1. Using `cargo-aur-packer` (Source Package - Recommended)

This method builds the package from source on your machine.

1.  **Install `cargo-aur-packer`**:
    ```bash
    cargo install cargo-aur-packer
    ```

2.  **Clone this repository**:
    ```bash
    git clone https://github.com/NiGhT-exe/hello-world.git
    cd hello-world
    ```

3.  **Generate AUR package files**:
    ```bash
    cargo aur-packer
    ```

4.  **Navigate to the package directory**:
    ```bash
    cd target/aur-package
    ```

5.  **Build and install the package**:
    ```bash
    makepkg -scCi
    ```
    *(The `-i` flag will install the package after a successful build. You can also use `makepkg -scC` to build, then `yay -U *.pkg.tar.zst` or `sudo pacman -U *.pkg.tar.zst` to install).*

### 2. Using `cargo-aur` (Binary Package)

This method packages the pre-compiled binary.

1.  **Install `cargo-aur`**:
    ```bash
    cargo install cargo-aur
    ```

2.  **Clone this repository**:
    ```bash
    git clone https://github.com/NiGhT-exe/hello-world.git
    cd hello-world
    ```

3.  **Generate AUR package files**:
    ```bash
    cargo aur
    ```

4.  **Navigate to the package directory**:
    ```bash
    cd target/cargo-aur
    ```

5.  **Build and install the package**:
    ```bash
    makepkg -scCi
    ```
    *(Similarly, `-i` installs. Or use `makepkg -scC` then `yay -U *.pkg.tar.zst` or `sudo pacman -U *.pkg.tar.zst`)*.

## Running the Application

Once installed, you should be able to run the application by typing:
```bash
hello
```

## Uninstalling the Application

### 1. Using `cargo-aur-packer`

```bash
yay -R hello-git hello-git-debug
```

### 2. Using `cargo-aur`

```bash
yay -R hello-bin hello-bin-debug
```

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.