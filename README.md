# Display_git_branch_in_terminal
Displays which branch your working on before the cursor when accessing the project in the terminal. 
Simply add the code to your ~/.bashrc file and watch the magic. Enjoy!

parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
PS1='\[\e[32m\]@\h\[\e[34m\]\w \[\e[33m\]\$ \[\e[0m\]$(parse_git_branch) '
