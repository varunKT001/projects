# Instructions

Now that we have completed the gallery, it's time to add some finishing touches, by completing the footer of the project.

1. Adding the footer tag as a sibling to the #gallery-container.

    ```html
    <footer>
    </footer>
    ```

2. Creating two `<p>` tags inside the `footer`
    Create the first `<p>` tag and give it an ID of `footer-title` and add the text "Multiverse Gallery Project"

    Now create a second `<p>` tag and give it an ID of `about` and add the text about inside.

3. Add the about icon inside the `#about` tag.
    Add the icon `assets/about.svg` inside the `#about` tag.

    Now the HTMl Structure is done, let's add some styles to the footer.

4. Set the background color of the footer tag to `#1f2224`

5. Now that we have made the background for the footer dark, we need to make the text color of the footer light. So, make the color of the footer to `white`

6. Make the footer fixed, by adding position fixed and setting the `left` and `bottom` values to `0px`

7. Make the footer a flex container and give an equal space between the about and footer title. Set the `justify-content` to `space-between` and `align-items` to `center`.

    ```css
        footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
    ```

We have completed the project, make sure that everything is working fine. Make All the steps as done, and submit the project.

Congratulations, you have come a long way! You have completed the project and learned a lot of new things. Take up the next [project](https://codedamn.com/projects) and start building on your own.
