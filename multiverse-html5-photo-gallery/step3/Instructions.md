# Instructions

Let's start adding styles to our page.

Flexbox layout is a best way to arrange elements in a flexible way on a single direction. It is a great way to organize your page and make it responsive across all viewports.

1. Making the `#gallery-container` to a flex container.

    Our agenda is to make the images responsive and occupy the whole width of the page. To do that, we need to make the `#gallery-container` to a flex container.

    ```css
    #gallery-container {
        display: flex;
        flex-wrap: wrap;
    }
    ```

2. Now let's set the width, height and object-fit of the images. So they maintain the aspect ratio and occupy the whole width of the article.

    ```css
    .gallery-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
    ```

3. Set the position of the article `.img-container` to relative and set the flex property to `1 0 100%`. The `flex` property is the shorthand for `flex-grow`, `flex-shrink` & `flex-basis` properties.

    ```css
        .img-container {
            position: relative;
            flex: 1 0 100%;
        }
    ```

    Now the flex-container will occupy the complete width of the page.

4. Let's make sure that the `.title` is visible properly.

    ```css
        .title {
            position: absolute;
            bottom: 0.5em;
            left: 0.5em;
            font-family: "Source Sans Pro", sans-serif;
            color: white;
            }
    ```

5. Let's add the media queries so that the images are responsive across all viewports.

    ```css
    @media (min-width: 768px) {
        .img-container {
            flex: 1 0 50%;
        }
    }

    @media (min-width: 1280px) {
        .img-container {
            flex: 1 0 33.333%;
        }
    }
    ```

We have finally complete the gallery and made it responsive. Let's add the footer to the project.
