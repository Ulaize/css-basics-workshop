# CSS Workshop #2

## Operational instructions
* Fork this repo and create a clone in Cloud9
* Each exercise goes to a different branch, branched from master
* When you complete an exercise create a pull request for it
* Check back often for comments on your pull requests
* When you respond to a pull request comment by making a new commit, @mention the person in a new comment inside the PR

## Technical instructions
* The repo already contains a `css/` directory with a `normalize.css` as well as a `main.css`. You should be spending
most of your time in `main.css`.
* There is an `index.html` file at the root of the repo which links to `normalize.css` and `main.css`. This is where
you would put your HTML code for the exercise. Should you need to add any new CSS files, make sure you respect the
ordering and have your CSS files be the last to be loaded.

## Exercise 1: Navigation menu
* Create an HTML page with a navigation menu of 5 items. You can make the links point to anything, like google.com
  * Home
  * Products
  * Services
  * About us
  * Contact us
* Below the navigation menu, add a dozen of "lorem ipsum" paragraphs. In Cloud9 if you write `lorem` followed by
a **`TAB`**, it will expand into a paragraph of lorem. **PROTIP**: if you type `p(lorem)*12` and then press `TAB`, it
will expand into 12 paragraphs of lorem :)
* Give the navigation menu a 50% opaque black background
* Give the menu elements a white border, white text and a nice padding of `0.5em`
* Notice that even though the padding is the same all around, the list elements seem to have more vertical spacing
* This is because the `line-height` property, which sets the "height of a standard line of text", is larger than
the font size. Set the `line-height` property of the menu elements to `1`, and notice the difference.
* Fix the browser default `padding` and `margin` on your `ul` element by resetting it to `0`
* Make the navigation menu **`fixed`** on top of the page, taking the full width of the page (100%)
* Give the navigation menu a padding of `0.5em`.
* Notice that the navigation menu now goes overboard on the right of the page! What is happening?
* Setting the `width` to `100%` and then adding a `padding` will make the width of the nav go over 100%. This is
because the browser's default box sizing model (`content-box`) adds paddings and borders on top of your defined width/height.
* There is a better box sizing model, `border-box`, that takes your defined `width` as being `width_of_content + width_of_padding + width_of_border`.
* Read more about [box sizing on Paul Irish's blog](http://www.paulirish.com/2012/box-sizing-border-box-ftw/) and copy/paste his fix at the **top** of your `main.css`
* Refesh your page to see that the width is now back to 100% total.
* **IMPORTANT**: You should add this snippet of code to the top of your `main.css` for *all future exercises!* You can either
do it every time, or commit it once to master and branch off of there. Your choice.
* Commit/push and make a pull request
* Your end-result should look somewhat like this:
![exercise 1](https://i.imgur.com/NutCbP6.png)

## Exercise 2: CSS Positioning and Box Model
* Add the following HTML to the `body` of an empty HTML page:
```html
<aside class="dialog-box">
    <h1 class="dialog-box__title">Hello World</h1>
    <div class="dialog-box__content">
        <p>
            Lorem ipsum dolor sit amet, consectetuer adipiscing elit,
            sed diam nonummy nibh euismod tincidunt ut laoreet dolore
            magna aliquam erat volutpat. Ut wisi enim ad minim veniam,
            quis nostrud exerci tation ullamcorper suscipit lobortis nisl
            ut aliquip ex ea commodo consequat. Duis autem vel eum iriure
            dolor in hendrerit in vulputate velit esse molestie consequat,
            vel illum dolore eu feugiat nulla facilisis at vero eros et
            accumsan et iusto odio dignissim qui blandit praesent luptatum
            zzril delenit augue duis dolore te feugait nulla facilisi.
            Nam liber tempor cum soluta nobis eleifend option congue
            nihil imperdiet doming id quod mazim placerat facer possim
            assum. Typi non habent claritatem insitam; est usus legentis
            in iis qui facit eorum claritatem. Investigationes
            demonstraverunt lectores legere me lius quod ii legunt saepius.
            Claritas est etiam processus dynamicus, qui sequitur mutationem
            consuetudium lectorum. Mirum est notare quam littera gothica,
            quam nunc putamus parum claram, anteposuerit litterarum formas
            humanitatis per seacula quarta decima et quinta decima. Eodem
            modo typi, qui nunc nobis videntur parum clari, fiant sollemnes
            in futurum.
        </p>
    </div>
    <button class="dialog-box__close"></button>
</aside>
```
* Using CSS, make the dialog box look like this:
![exercise-2](https://i.imgur.com/xSQLLaB.png)
* Here are a few indications to get you started:
  * The style of writing in this HTML is inspired from BEM. [Read about BEM](https://css-tricks.com/bem-101/) on your own
  time for educational purposes. Basically, each stylable element is assigned a class name based on the "component" it is in.
  * Use the following CSS skeleton to get started:
```css
.dialog-box {
    background-color: #d2d2d2;
}
.dialog-box__title {
    
}
.dialog-box__content {
    background-color: #f2f2f2;
}
.dialog-box__close {
    border: 2px solid white;
    background-color: tomato;
    width: 24px;
    height: 24px;
}
```
  * You shouldn't need to add any more selectors, only fill in the provided ones.
  * Make sure the content is spaced away from the borders of its containers.
  * You will need to remove the default margin on the `h1` element

## Exercise 3: CSS Layouts and Media Queries
* **NOTE**: As you are doing this exercise, take note of how painful it is to do a responsive layout. In general, when
building pages, we will be using a CSS library such as Twitter's Bootstrap or Zurb's Foundation. In this class we will
be looking at [Zurb's Foundation](http://foundation.zurb.com/). It comes with a complete [documentation](http://foundation.zurb.com/docs/)
* For this exercise though, we will be doing the layouts manually, just to see there is no magic involved.
* In this exercise we will be creating a responsive image thumbnail gallery.
* The result should look like this on desktop:
* ![exercise-3-desktop](https://i.imgur.com/YAydktA.png)
* The result should look like this on a tablet:
* ![exercise-3-tablet](https://i.imgur.com/hCUKDBJ.png)
* The result should look like this on a mobile:
* ![exercise-3-mobile](https://i.imgur.com/7gtkfso.png)
* **NOTE**: You will need to add the following line to the `head` of your HTML document

## Exercise 4: Foundation version of the gallery
* We are going to be re-doing our responsive gallery using exclusively Foundation's library
* [Download the foundation esentials](http://foundation.zurb.com/develop/download.html) and extract the file `foundation.css`
* Add this file to your `css` directory and `link` it in the `head` of your page. **Pay attention** to the ordering of your included CSS!
* Re-create the responsive image gallery using [Foundation's Block Grid](http://foundation.zurb.com/docs/components/block_grid.html)

## Exercise 5: Foundation's responsive grid
* Read about [Foundation's responsive grid](http://foundation.zurb.com/docs/components/grid.html)
* Look at [Foundation's HTML templates](http://foundation.zurb.com/templates.html) for a ton of practical examples
of how to use the grid
* Create the following page using Foundation's responsive grid
* On desktop:
* ![desktop](https://i.imgur.com/73r4tul.png)
* On tablet:
* ![tablet](http://i.imgur.com/h4ChQlj.png)
* On mobile:
* ![mobile-1](https://i.imgur.com/oQv6on0.png)
* ![mobile-2](https://i.imgur.com/PixTV2W.png)
