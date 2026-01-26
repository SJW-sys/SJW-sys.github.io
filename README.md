Hugo is one of the most popular open-source static site generators written in GO. With a focus on speed and flexibility. I will be using this so I can focus mostly on writing verses designing and maintaining a website from scratch.

Install on Debian:
    sudo apt install hugo

Setup With GitHub Pages:
    have hugo installed (see above section)

    start a new hugo site via command:
        hugo new site USERNAME.github.io

    get into files:
        cd USERNAME.github.io

    initialize repo:
        git init

    Find your theme you want, then go to its repo, typically they will have a "install", some sort of git clone URL . Run that command, ie.
        git submodule add https://github.com/clente/hugo-bearcub themes/hugo-bearcub

    add theme to the hugo toml config, ie
        echo 'theme = "hugo-bearcub"' >> hugo.toml

    Generate content
        hugo new content content/blog/test.md
    
    launch hugo locally to test
        hugo server -D

    modify hugo.toml config for site via your hugo.toml in /root dir for initial configuration, recommend using example site config as a base for most themes.

    be sure to check your content directory for index files and setup for your web pages.

    push to your github when ready
    

resources:
    hugo install: https://gohugo.io/installation/linux/
    hugo themes: https://themes.gohugo.io/themes
    hugo theme (bearcub): https://github.com/clente/hugo-bearcub?tab=readme-ov-file
    Hugo with Github Pages: https://www.testingwithmarie.com/posts/20241126-create-a-static-blog-with-hugo/