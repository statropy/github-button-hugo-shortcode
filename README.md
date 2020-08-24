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
- `view`

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
- Default: `false`

Attach the applicable number to the button for the specified type.

#### `dark`

- Type: `string`, `true` to enable
- Usage: `optional`
- Default: `false`

Use the dark button theme if enabled, otherwise light theme.

#### `large`

- Type: `string`, `true` to enable
- Usage: `optional`
- Default: `false`

Use a larger button if enabled.

#### `branch`
 - Type: `string`
 - Usage: `optional` for `download`
 - Default: `master`

Specify a branch other than master for the download.

#### `icon`
 - Type: `string`
 - Usage: `optional`

Override the default icon for a button type. Valid icons are
 - `mark-github`
 - `heart`
 - `eye`
 - `star`
 - `repo-forked`
 - `repo-template`
 - `issue-opened`
 - `download`

#### `text`
 - Type: `string`
 - Usage: `optional`

Override the default button text for a button type.

#### `aria_label`
 - Type: `string`
 - Usage: `optional`

Override the default aria-label for a button type.

## Defaults

| button   | icon          | text              | path https://github.com             | aria-label                                |
| -------- | ------------- | ----------------- | ----------------------------------- | ----------------------------------------- |
| follow   | mark-github   | Follow @`user`    | /`user`                             | Follow @`user` on GitHub                  |
| sponsor  | heart         | Sponsor           | /sponsors/`user`                    | Sponsor @`user` on GitHub                 |
| watch    | eye           | Watch             | /`user`/`repo`/subscription         | Watch `user`/`repo` on GitHub             |
| star     | star          | Star              | /`user`/`repo`                      | Star `user`/`repo` on GitHub              |
| fork     | repo-forked   | Fork              | /`user`/`repo`/fork                 | Fork `user`/`repo` on GitHub              |
| template | repo-template | Use this template | /`user`/`repo`/generate             | Use this template `user`/`repo` on GitHub |
| issue    | issue-opened  | Issue             | /`user`/`repo`/issues               | Issue `user`/`repo` on GitHub             |
| download | download      | Download          | /`user`/`repo`/archive/`branch`.zip | Download `user`/`repo` on GitHub          |
| view     | mark-github   | `repo`            | /`user`/`repo`                      | View `user`/`repo` on GitHub              |

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
{{< github_button button="view"     user="statropy" repo="github-button-hugo-shortcode" >}}
```

## Install

Add the snippet from `layouts/partials/head.html` to the head.html in the project or theme. This loads the button script on each page that includes a button.

Add `layouts/shortcodes/github_button.html` to the `layouts/shortcodes` folder of the project or theme.

Add the shortcode to a page

`{{< github_button button="follow" user="statropy" >}}`
