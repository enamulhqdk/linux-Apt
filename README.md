# linux-Apt

# APT & System Updates Assignment

## Part 1: Understanding APT & System Updates (15 min)

### 1. Check your system’s APT version

```sh
apt --version
```
![alt text](image.png)

**Output:**

```sh
apt 2.2.4 (amd64)
```

### 2. Update the package list

```sh
sudo apt update
```
![alt text](image-1.png)

**Why is this step important?**

- Fetches the latest package lists from repositories.
- Ensures system awareness of the latest package versions.

### 3. Upgrade installed packages

```sh
sudo apt upgrade -y
```
![alt text](image-3.png)

**Difference between **``** and **``**:**

- `update`: Fetches the latest package list but does not install updates.
- `upgrade`: Installs available package updates.

### 4. View pending updates

```sh
apt list --upgradable
```
![alt text](image-4.png)

**Pending updates recorded.**

## Part 2: Installing & Managing Packages (20 min)

### 5. Search for a package using APT

```sh
apt search image editor
```
![alt text](image-5.png)

**Selected package:** `gimp`

### 6. View package details

```sh
apt show gimp
```
![alt text](image-6.png)

**Dependencies:** Listed in "Depends" section.

### 7. Install the package

```sh
sudo apt install gimp -y
```
![alt text](image-7.png)

**Verification:** Package installed successfully.

### 8. Check installed package version

```sh
apt list --installed | grep gimp
```
![alt text](image-8.png)


**Installed version:** `gimp 2.10.30-1`

## Part 3: Removing & Cleaning Packages (10 min)

### 9. Uninstall the package

```sh
sudo apt remove gimp -y
```
![alt text](image-9.png)

**Package removed successfully.**

### 10. Remove configuration files

```sh
sudo apt purge gimp -y
```


**Difference between **``** and **``**:**

- `remove`: Keeps configuration files.
- `purge`: Deletes configuration files.

### 11. Clear unnecessary dependencies

```sh
sudo apt autoremove -y
```
![alt text](image-11.png)

**Importance:** Removes orphaned packages.

### 12. Clean up downloaded package files

```sh
sudo apt clean
```
![alt text](image-13.png)

**Function:** Frees disk space by deleting cached package files.

## Part 4: Managing Repositories & Troubleshooting (15 min)

### 13. List all APT repositories

```sh
cat /etc/apt/sources.list
```
![alt text](image-14.png)

**Observations:** Contains URLs of package sources.

### 14. Add a new repository

```sh
sudo add-apt-repository universe
sudo apt update
```
![alt text](image-15.png)

**Universe Repository Content:** Community-maintained packages.

### 15. Simulate an installation failure

```sh
sudo apt install fakepackage
```

**Error message:** Package not found.

**Troubleshooting steps:**

- Verify package name.
- Ensure repository is enabled.
- Run `sudo apt update`.
![alt text](image-16.png)


