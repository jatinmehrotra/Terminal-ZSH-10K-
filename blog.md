>**Are you a Developer who extensively uses Terminal? Are you a DevOps who is bored of the trivial, inefficient terminal and its ancient colour and shapes? Least of all; are you a terminal fanatic who believes in the power of terminal, and prefers typing less.**
>
>This article talks about transforming our **dull terminal** into blazing-fast, productive and intuitive one which has memory, syntax-highlighting and default support for git.
>
>*After this, your terminal will make you feel like a 10x developer. 🤩*
>

### Prequesites

- [Zsh shell](https://www.zsh.org) 
- [Homebrew package manager](https://brew.sh)
 
 **Note**: This article uses **macOS** but the same is applicable for Linux and Windows distributions.

## Unleash Terminal => 100 level

 **Follow along sequentially to get the best results. Whenever you add a plugin or change configuration, it is important to restart terminal or source it until we add Zsh reload plugin.***

### Iterm2

- [Iterm2](https://iterm2.com/downloads.html) is the `dextrous heir` of the default old-fashioned terminal.
- It is known as the successor because of its [amazing out-of-the-box features](https://iterm2.com/features.html) like **split panes, searches, autocomplete, flexibility to configure.**

  ![iterm2](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-9.48.57-PM-scaled.jpg)

- You can also edit preferences of iterm2 and choose colour schemes according to your preference.

  ![iterm preferences](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-10.20.11-PM.jpg)


## Oh My Zsh 

- Simply put, it's a [tool/framework](https://ohmyz.sh) which allows us to `manage Zsh configuration, use robust plugins and stunning themes`
 
 - **Plugins**: This allows us to add the functionality of different types to our iterm2 just by enabling them in zsh configuration. Here is the [list of plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins) supported by this framework.
 
 - **Themes**: This allows us to tweak the colours and aesthetics of the iterm2 terminal. They beautifies our terminal. My preffered Oh My Zsh theme is ```agnoster``` but there are around [150 themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) to choose from. 
 
 - After installing iterm2 and Oh My Zsh, edit ```~/.zshrc``` and set ```ZSH_THEME="agnoster" ``` BUT, THE REAL BEAUTY COMES from `powerlevel10k theme`.
 - Restart your terminal to see the changes.

    ![agnoster](https://user-images.githubusercontent.com/49100982/108254745-777cb400-716c-11eb-800a-a8cfa612253f.jpg)
 
 

## Powerlevel10k

- [Powerlevel10k](https://github.com/romkatv/powerlevel10k#configuration-wizard) can be confusing by the name, but actually, it's a theme for Zsh.

- I like Powerlevel10k theme more than the Oh My Zsh themes, because this aims at **speed, flexibility and easy customization.**

![Powerlevel10k](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-9.43.48-PM-scaled.jpg)

- After installation, set ```ZSH_THEME="powerlevel10k/powerlevel10k"``` in ```~/.zshrc.``` Restart your iterm2 for the change to take effect.
 
- On Restart Powerlevel10k Configurator will show up, choose preferred UI options. Finish the wizard.

 **Note**: If you are not happy with your choices, you can run ```p10k configure``` command to re-run your configuration.

 ![p10k configure wizard](https://raw.githubusercontent.com/romkatv/powerlevel10k-media/master/configuration-wizard.gif)

 **Note** : You can even customise powerlevel10k prompt by editing  ```~/.p10k.zsh``` file.


## Adding Plugins 

- Till now, we have tweaked the way our iterm2 will look and looked upon the features iterm2 and powerlevel10k provides, but still we haven't touched on **plugins**.

- Plugins will upgrade the functionalities of our iterm2 terminal and make our life easy as a terminal user.

- Oh My Zsh provides around [150+ plugins](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins), and there are also some plugins that are provided by the open-source community.

- In this article, I will be covering **my favourite plugins**, once you know how to add plugins to Oh My Zsh, then you can play around and add others based on your preferences.

  ### Zsh Syntax Highlighting
 
   - This is one of the plugins which are not provided by **Oh My Zsh**.
   - For installation

      ```
      brew install zsh-syntax-highlighting
      ```

   - Add this to the end of the **~/.zshrc** 


      ```
      source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
      ```
  - Wrong commands are highlighted in **red** and correct commands in **green**.

      ![Syntax highlighting](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-9.28.34-PM.png)

      ![syntax highlighting](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-6.11.16-PM.png)
 
  ### Zsh Autosuggestions
   - This is one of the most favourite plugins, a total lifesaver. 
   - You’ll see a suggested completion come up in faded grey colour as you type.
   - If you hit the right arrow key, it will fill in the suggestion. If you hit the tab, it will list more suggestions below it.
  
  

   - **Note**: This is the only plugin from Oh My Zsh which requires us to install it first 
  
      ```
        git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
      ```

   - Add this to **~/.zshrc** under plugins and restart terminal.
  
      ```
      plugins=(git
      zsh-autosuggestions
      zsh-completions
      )
      ```

      ![Autosuggestions](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-9.25.59-PM.png)
  ### Zsh Reload
   - Every time we add a plugin or making some configuration changes to Zsh, we need to restart or **source** it to refresh.

      ```
      plugins=(git
      zsh-autosuggestions
      zsh-completions
      zsh_reload
      )
      ```
   - This plugin is real time saver, now instead of restarting just type src in the iterm2 to make changes effective ( ofcourse to make it effective we need to restart iterm2 after we add this plugin 🤷‍♂️).


      ![Zsh reload](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-9.30.02-PM.png)


  ### Web Search
   - There are times when we need to google a bug, using this plugin we can do it like a boss.

      ```
      plugins=(git
      zsh-autosuggestions
      zsh-completions
      zsh_reload
      web-search
      )
      ```
   - Type ```src``` instead of restarting iterm2 ( thanks to reaload plugin) and then type ```google something.```
   - a new google search will pop in your default browser.
    ![Web search](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-9.33.00-PM.png)
    ![google search](https://travis.media/gifs/web-search-gif.gif)
   


-  ### Bonus ( Visual Studio Code config )

   - If you like to use **Terminal** in your VS Code, after all these tweaks, you might see something unusual in your terminal ( missing icons, fonts)
  
      ![broken vscode](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-7.06.20-PM.png)
   - To fix this, Go to Preferences -> Settings -> search for **settings.json** -> and add this on 4th line. ```"terminal.integrated.fontFamily": "'MesloLGS NF'"```.
  

      ![vs code setings](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-6.21.30-PM.png)


      ![vs code json](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/09/Screenshot-2021-09-04-at-6.22.54-PM.png)
   - Your VS Code terminal will be fixed.


## Sum-up

In this article, we saw how some simple tweaks and few plugins can make such a huge difference in our day-to-day life whether you are a Developer or DevOps or a Linux Geek.

Till then, **Happy Learning!** 