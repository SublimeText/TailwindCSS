![Tailwind CSS](https://raw.githubusercontent.com/SublimeText/TailwindCSS/master/assets/screen.png)

# Tailwind CSS

A [Sublime Text](http://www.sublimetext.com) CSS syntax extension with support for [Tailwind CSS](https://tailwindcss.com)

_Requires ST 4092 or higher._

## Install

**Package Control:**

1. Open `Command Palette` using menu item `Tools → Command Palette` or `CMD/CTRL` + `SHIFT` +`P`.
2. Choose `Package Control: Install Package`.
3. Type `Tailwind CSS` and press `ENTER`.

**Manually:**

1. Download latest release and unzip. it into your Packages folder.
2. Go to `Sublime Text → Preferences → Browse Packages`.
3. Move folder to inside and rename the folder to `Tailwind CSS`.

## Usage

### CSS

This syntax is assigned to files which end with `tailwind.css` by default.

To use it for ordinary `*.css` files manual assignment is needed.

1. Click onto the syntax name in the status bar
2. Navigate to the sub menu `Open all with current extension as...`
3. Click on `Tailwind CSS`.

To add highlighting for Tailwind @-rules to CSS in a way they are also supported within component syntaxes like [Svelte](https://packagecontrol.io/packages/Svelte) or [VueJS](https://packagecontrol.io/packages/Vue%20Syntax%20Highlight)...

1. create a custom _Packages/User/CSS (Tailwind).sublime-syntax_
2. paste the following content:

   ```yml
   %YAML 1.2
   ---
   name: CSS (Tailwind)
   scope: source.css
   version: 2
   
   extends:
     - Packages/Tailwind CSS/Tailwind CSS.sublime-syntax
   ```

> [!WARNING]
>
> By assigning `source.css` main scope original PostCSS syntax is augmented.
> 
> 1. Augmenting syntax must be loaded after CSS in order for this trick to work.
> 2. Only a single augmenting syntax may exist.
> 3. Syntaxes, which extend core CSS to add their own rules can't be augmented this way.

### PostCSS

To add highlighting for Tailwind @-rules to PostCSS in a way they are also supported within component syntaxes like [Svelte](https://packagecontrol.io/packages/Svelte) or [VueJS](https://packagecontrol.io/packages/Vue%20Syntax%20Highlight)...

1. create a custom _Packages/User/PostCSS (Tailwind).sublime-syntax_
2. paste the following content:

   ```yml
   %YAML 1.2
   ---
   name: PostCSS (Tailwind)
   scope: source.postcss
   version: 2
   
   extends:
     - Packages/Tailwind CSS/Tailwind CSS.sublime-syntax
     # - ... maybe more additions
     - Packages/PostCSS/PostCSS.sublime-syntax
   ```

> [!WARNING]
>
> By assigning `source.postcss` main scope original PostCSS syntax is augmented.
> 
> 1. Augmenting syntax must be loaded after PostCSS in order for this trick to work.
> 2. Only a single augmenting syntax may exist.

> [!NOTE]
>
> requires:
> - [Sublime Text build 4152+](https://www.sublimetext.com/download)
> - [PostCSS 3.0.0+](https://packagecontrol.io/packages/PostCSS)

### SCSS

To add highlighting for Tailwind @-rules to SCSS in a way they are also supported within component syntaxes like [Svelte](https://packagecontrol.io/packages/Svelte) or [VueJS](https://packagecontrol.io/packages/Vue%20Syntax%20Highlight)...

1. create a custom _Packages/User/SCSS (Tailwind).sublime-syntax_
2. paste the following content:

   ```yml
   %YAML 1.2
   ---
   name: SCSS (Tailwind)
   scope: source.scss
   version: 2
   
   extends:
     - Packages/Tailwind CSS/Tailwind CSS.sublime-syntax
     # - ... maybe more additions
     - Packages/Sass/Syntaxes/SCSS.sublime-syntax
   ```

> [!WARNING]
>
> By assigning `source.scss` main scope original PostCSS syntax is augmented.
> 
> 1. Augmenting syntax must be loaded after PostCSS in order for this trick to work.
> 2. Only a single augmenting syntax may exist.

> [!NOTE]
>
> requires:
> - [Sublime Text build 4152+](https://www.sublimetext.com/download)
> - [Sass 4.0.0+](https://packagecontrol.io/packages/PostCSS)

## Related Extensions

- [LSP-tailwindcss](https://github.com/sublimelsp/LSP-tailwindcss)

## Troubleshooting

Tailwind CSS extends Sublime Text's CSS syntax definitions.

If Tailwind CSS syntax highlighting doesn't work and console displays syntax errors in _Tailwind CSS.sublime-syntax_, please make sure to remove any out-dated syntax override.

Steps:

1. call _Menu > Preferences > Browse Packages.._
2. Look for _CSS_ folders
3. Remove it or at least delete any syntax definition in it.
