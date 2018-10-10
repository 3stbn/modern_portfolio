A vuepress portfolio designed by **bradtraversy** and addapted to **vuepress** by **3stbn**

## Instalation

You can use npm install but according to the vuepress documentation is better to use yarn due to webpack issues

 - yarn install
 - yarn dev
## Use

You can easily edit the static parts with html in the md files . To add portfolio items just create new md file on the portfolio folder and add the meta data at the top of the file like follows:

    ---
    title: Project 1
    category: portfolio
    img: ./project1.jpg
    ref: github
    extLink: https://github.com/
    description: your description
    tages: [html, css, php]    
    ---
    <PortfolioContent />

To add the main image just copy your image on:

    .vuepress/public/project1.jpg
and link it on the md file as:

     img: ./project1.jpg
Soported project references:

 - github 
 - dribbble 
 - behance
