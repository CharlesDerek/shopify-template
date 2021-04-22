# Shopify Theme Development Tutorial 2021

## Set up Shopify
- Create Shopify Account (Free Trial or Partner Account)
- Create A Store
- Customize Theme
- Set up Private App -> Enable Theme Read/Write

## Set up Git
- Install Git
- Create Folder for Shopify Theme
- Create Git Repository (git init)
- Sync Folder to Git Repository
- (optional) Create a README.md file add and push to repo
- Commit Progress

## Set up Themekit
- Install Themekit
- Download Theme with Theme Kit
- Install Node Wrapper for Theme Kit (https://www.npmjs.com/package/@shopify/themekit)

## Set up Sass
- Install Sass
- Set up SASS Folder/File Structure

## Set up Gulp
- Install Gulp
- Create Gulpfile
- Write Tasks (sass, watch, clean)
                const gulp = require('gulp');
                const themeKit = require('@shopify/themekit');
                const sass = require('gulp-sass');
                const clean = require('gulp-clean-css');

                gulp.task('sass', function() {
                    return gulp.src('scss/global.scss')
                    .pipe(sass())
                    .pipe(clean( { compatibility: 'ie11' }))
                    .pipe(gulp.dest('assets'))
                });

                gulp.task('watch', function() {
                    gulp.watch('scss/*.scss', gulp.series('sass'))
                    themeKit.command('watch', {
                        allowLive: true,
                        env: 'development'
                    })
                });
- Add CSS file to theme.liquid inside <head>

## Customizing Your Theme
- Edit Shopify Theme Code
- Shopify Liquid
- Modifying a Section
- Creating a new Section

## VS Code Extensions
- VS Code Extensions for Shopify Development