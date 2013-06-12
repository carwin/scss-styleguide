# SASS Styleguide

![SASS](http://sass-lang.com/images/sass.gif)

This is a loose guide for formatting our SASS stylesheets to encourage
consistency. There will probably be exceptions.

## Basics

  * Use only soft tabs equalling two spaces. No hard TABs.
  * Remove trailing whitespace.
  * Don't define a unit for 0 values. (0px)
  * `//` comments will not be rendered on compile.
  * Files should end with a newline

## Indention & Spacing

  * Starting level selectors should have no indention.
  * Attributes should be indented once (two spaces) under their selectors.
  * One space should follow a selector name before the opening declaration bracket.
  * Add one space between an attribute (after the colon) and value.
    _ex:_

    ```css
    .above-menu {
      text-align: center;
      vertical-align: middle;
    }
    ```

### Rules for SASS Nesting

Please try to limit the nesting of selectors as much as possible. Nesting tends
to lead to specificity problems.

  * Nested declarations should be indented once (two spaces) under their parent.
  * Follow global rules for spacing.

#### Selector Nesting

  * A newline should precede and follow a selector nesting.
  * Place nested selectors after the parent's attributes/includes/extends/etc...
    _ex:_

    ```css
    .above-menu {
      text-align: center;
      vertical-align: middle;

      li {
        color: #cecece;
      }

    }
    ```

#### SASSy Nesting

  * @includes etc... should be placed (when sensible) at the end of a selectors attributes. Specifically, add any breakpoint mixins in order of progressive enhancement.
  * Don't use a precedeing or following newline on nested declarations of this sort.
    _ex:_

    ```css
    .above-menu {
      text-align: center;
      vertical-align: middle;
      @include breakpoint(tall) {
        vertical-align: top;
      }

      li {
        color: #cecece;
        @include breakpoint(tall) {
          color: #bbbbbb;
        }
        @include breakpoint(grande) {
          text-decoration: underline;
        }
      }

    }
    ```

## Comments
  * Separate __Sections__ within a file using this comment style to
    declare a Section:

    ```css
    // Here is a "Section comment."
    // -----------------------------
    ```
  * Optionally, describe markup related to components like so:

    ```css
    // ------------------------------------------------------------------
    // <div class="my-component">
    //   <img class="my-component__image">
    //   <div class="my-component__stuff">
    //     Some stuff in here
    //   </div>
    // </div>
    // ------------------------------------------------------------------
    ```

  * Keep comments _inside_ the selectors they comment on, not above. Append your
    GitHub username after the comment if relevant -- this way other developers
    will know who to go to if questions arise. Here's an example:

    ```css
    .selector-name {
      // - This is an inline comment, the dash at the
      //   beginning helps separate ideas.
      // - See?
      //                                    -- @carwin
      background: #000000;
      color: #ffffff;
    }
    ```

