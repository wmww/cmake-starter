# A basic CMake C++ starter project

## To download and compile

```bash
# Change directory into the one you want to contain your new project directory
cd ~/Desktop

# Download the project from GitHub
git clone https://github.com/wmww/cmake-starter.git

# 'Move' (change the name) of the newly created project directory
mv cmake-starter your-project-name

# Change directory into the new project
cd your-project-name

# Create a 'build' directroy for CMake inside the main project directory
mkdir build

# Move into it
cd build

# Initialize CMake (.. is the parent directory, where it will look for a CMakeLists.txt)
cmake ..

# Compile the program
make

# Run the program
# . is the current directory, so './program' should be the same as just 'program'
# Specifically in the case of running executables however, the latter doesn't work
./program

# A cool trick to compile and then run the program, but only if compiling succeeds
make && ./program
```

Your directory structure should now look like this:

* `~/Desktop` (or wherever else you put the project)
  * `your-project-name` (all the files of your project stay in here)
    * `build` (you must be in here to run 'make')
      * `.o` files, and other things used by cmake and make to compile and link
    * `.git` (hidden)
      * All the special files git uses to do its magic
    * `CMakeLists.txt` (describes how to compile your project)
    * `readme.md` (the document you're reading now)
    * `.cpp` and `.h` files
    * `.gitignore` (specifies which files and directories git should not track (such as build)

Now that cmake is set up, you shouln't need to run `cmake ..` anymore. When you change your source code, just running `make` is sufficient to recompile. When you add source files you'll need to also add them to CMakeLists.txt. When this happens, the `make` command will automatically run CMake.

The build directory is not tracked by git (.gitignore makes sure of that) thus not uploaded to GitHub. If you ever get the feeling something got screwed up, you can always delete build, recreate it and rerun CMake.

## To use your own GitHub repo

```bash
# Disconnect from my CMake starter project
git remote remove origin
```

Next we need to create an online repo. If using GitHub:
1. Sign in
2. "+" -> "New repository" in the upper right
3. Make sure "Initialize this repository with a README" is **unchecked** and  "Add gitignore" and "Add license" are both set to **None**
4. Create the repository
5. Under "Quick setup", make sure HTTPS is selected instead of SSH
6. Follow instructions in the "…or push an existing repository from the command line" section

## To upload your changes to your new repo

Now whenever you make changes to the project, you want to tell git about them so you can upload them to your new repo:
```bash
# Stage the changes you've made (makes more sense when you use git in more complex ways)
# Note: You want to add your project's directory
#       If you are in the project's directory, you 'git add .'
#       I'm assuming you're in the build directory, which is in the project's directry
#       .. is the parent of the current directory, so 'git add ..' is what you want
git add ..

# Commit your changes with a message, ideally describing what you've done
git commit -m "Add such and such functionality"

# Upload your changes to GitHub or other online repo
git push
```

## To set up on another computor

The process is basically the same as the original setup. The only differences are you swap out the `git clone` address with your own, and you don't need to do any of the *To use your own GitHub repo* steps. To get your address for `git clone`:
1. Go to your repo's GitHub page
2. Click the green 'Clone or download' button
3. Make sure "Clone with HTTPS" shows (otherwise click "Use HTTPS")
4. Copy the address

