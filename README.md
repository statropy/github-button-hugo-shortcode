[![License](https://img.shields.io/badge/License-BSD%202--Clause-orange.svg)](https://opensource.org/licenses/BSD-2-Clause)

# github-button-hugo-shortcode

![all the GitHub buttons](/img/github-buttons-all.png)

Hugo shortcode for https://buttons.github.io/

Add this shortcode to a [hugo](https://gohugo.io/) theme or project. Add the shortcode to a hugo page markdown to display a GitHub button on the page.

[Read about how this shortcode was created at Statropy Software](https://statropy.com/blog/hugo-shortcode-github-button/)

## Usage

{{< github_button button="<button_type>" user="<user_name>" >}}

### Parameters

#### `button`

- Type: `string`
- Usage: `required`

This selects the type of button to display.

- `follow`
- `sponsor`
- `watch`
- `star`
- `fork`
- `template`
- `issue`
- `download`

#### `user`

- Type: `string`
- Usage: `required`

The GitHub username for the button link.

#### `repo`

- Type: `string`
- Usage: `required` for `watch`, `star`, `fork`, `template`, `issue`, `download`

The GitHub repo for the button link.

#### `count`

- Type: `string`, `true` to enable
- Usage: `optional` for `follow`, `watch`, `star`, `fork`, `issue`

Attach the applicable number to the button for the specified type.

#### `dark`

- Type: `string`, `true` to enable
- Usage: `optional`

Use the dark button theme if enabled, otherwise light theme.

#### `large`

- Type: `string`, `true` to enable
- Usage: `optional`

Use a larger button if enabled.

#### `branch`
 - Type: `string`
 - Usage: `optional` for `download`
 - Default: `master`

Specify a branch other than master for the download.

## Examples

Follow button and Follow button with followers count:

![follow](/img/follow-button.png)

```
{{< github_button button="follow" user="statropy" >}}
```

![follow and count](/img/follow-count-button.png)

```
{{< github_button button="follow" user="statropy" count="true" >}}
```

A large Star button with stargazers count in dark theme:

![customized star](/img/star-large-dark-count-button.png)

```
{{< github_button button="follow" user="statropy" repo="github-button-hugo-shortcode" count="true" large="true" dark="true" >}}
```

Download button for a branch named bugfix:

![download](/img/download-button.png)

```
{{< github_button button="download" user="statropy" repo="github-button-hugo-shortcode" branch="bugfix" >}}
```

All buttons:

![all the GitHub buttons](/img/github-buttons-all.png)

```
{{< github_button button="follow"   user="statropy" >}}
{{< github_button button="sponsor"  user="statropy" >}}
{{< github_button button="watch"    user="statropy" repo="github-button-hugo-shortcode" count="true" >}}
{{< github_button button="star"     user="statropy" repo="github-button-hugo-shortcode" count="true" >}}
{{< github_button button="fork"     user="statropy" repo="github-button-hugo-shortcode" count="true" >}}
{{< github_button button="template" user="statropy" repo="github-button-hugo-shortcode" >}}
{{< github_button button="issue"    user="statropy" repo="github-button-hugo-shortcode" count="true" >}}
{{< github_button button="download" user="statropy" repo="github-button-hugo-shortcode" >}}
```

## Install

Add the snippet from `layouts/partials/head.html` to the head.html in the project or theme. This loads the button script on each page that includes a button.

Add `layouts/shortcodes/github_button.html` to the `layouts/shortcodes` folder of the project or theme.

Add the shortcode to a page

`{{< github_button button="follow" user="statropy" >}}`
