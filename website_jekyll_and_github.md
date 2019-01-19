## Setting up a Jekyll website 

### Tools needed
   * Jekyll - a command line tool that is used to generate the website.
   * Ruby - a programming language used to develop Jekyll
   * RubyGems - is the [package manager](https://en.wikipedia.org/wiki/RubyGems) for Ruby
   * Homebrew - a [package manager](http://linuxbrew.sh/) for Linux and Windows. It is needed to install Ruby and RubyGems on a Linux or Windows machine.

1. Homebrew Installation
      * dependencies: build-essential, curl, file, git
      * On Debian/Ubuntu, enter command ```sudo apt-get install build-essential curl file git``` on terminal window to install the dependencies.

      * Install Homebrew:
        ```ruby
            git clone https://github.com/Homebrew/brew /.linuxbrew/Homebrew
            mkdir ~/.linuxbrew/bin
            ln -s ../Homebrew/bin/brew ~/.linuxbrew/bin
            eval $(~/.linuxbrew/bin/brew shellenv)
        ```
2. Ruby Installation
      * Enter the following command on terminal
        ```
          brew install ruby
        ```
3. Jekyll Installation
     * Use the following command
       ```
         gem install jekyll bundler
       ```
4. Create a website using Jekyll
     * Use the following command
        ```
         jekyll new  <name_of_website>
        ```
5. View website
     * Build using bundle and start server
       ```
        bundle exec jekyll serve
       ```

### References
1. https://ines.io/blog/the-ultimate-guide-static-websites-jekyll
2. https://www.youtube.com/watch?time_continue=416&v=yXXj9oYFXRI