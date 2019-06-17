# FontImageSourceMissingInMenuItem
This is a sample project that illustrates a possible bug with Xamarin.Forms Shell menuitems and FontImageSource.

You should be able to use FontImageSource to render glyph font as the image source with a Xamarin.Forms image.  Please see James Montemagno's article on how to use FontImageSource, <a href="https://montemagno.com/using-font-icons-in-xamarin-forms-goodbye-images-hello-fonts/" target="_blank">"Using Font Icons in Xamarin.Forms: Goodbye Images, Hello Fonts!"</a> for implementation details.

With Shell, the following XAML markup will draw an icon next to the text

```xml
<FlyoutItem Title="Icon Shows up">
        <FlyoutItem.Icon>
            <FontImageSource
                FontFamily="{DynamicResource MaterialFontFamily}"
                Glyph="{x:Static icons:MaterialDesignIconFont.InformationOutline}"
                Color="Black"/>
        </FlyoutItem.Icon>
        <ShellContent ContentTemplate="{DataTemplate local:AboutPage}" />
</FlyoutItem>
```

This XAML will not draw an icon

```xml
<MenuItem Text="Icon Missing">
    <MenuItem.IconImageSource>
        <FontImageSource
            FontFamily="{DynamicResource MaterialFontFamily}"
            Glyph="{x:Static icons:MaterialDesignIconFont.InformationOutline}"
            Color="Black"/>
    </MenuItem.IconImageSource>
</MenuItem>
```    

A screenshot from the app in this repository
![](https://github.com/anotherlab/fontimagesourcemissinginmenuitem/blob/master/screenshots/menuitem%201.png?raw=true)


