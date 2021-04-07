<img src="./readme-icon.png" alt="Supernova Logo" style="max-width:100%;">


[Supernova](https://supernova.io) is a design system platform that allows you to seamlessly translate your design system data to production-ready code. Supernova works with any platform or tech stack, is used by many developers and organizations around the world, and can help you save time by replacing manual and repetitive tasks that all developers hate. To learn everything Supernova, please check out our [developer documentation](https://developers.supernova.io/).


# SwiftUI Exporter


The SwiftUI Exporter allows you to **produce production-ready code for all product styles (such as colors) defined inside your design system** in such a way that you can immediately use them to style your application elements. Specifically, this exporter automates the coding of:

- [x] Color definitions
- [x] Text Styles
- [x] Gradients
- [x] Shadows
- [x] Borders
- [x] Radii
- [x] Measures

You can generate all production ready-code either manually using Supernova's [VS Code extension](https://marketplace.visualstudio.com/items?itemName=SupernovaIO.pulsar-vsc-extension), or automate your code delivery pipeline using Supernova [Design Continuous Delivery](https://supernova.io/automated-code-delivery).

For color, gradient and measure tokens, the exporter will generate extensions that expose all tokens through `Color.Token.tokenName`, `Gradient.Token.tokenName` or `AppMeasures.tokenName`.

```
import SwiftUI

extension Color {
    
    static let Token = Color.TokenColor()
    
    struct TokenColor {

        let primary = Color(.sRGB, red: 69/255, green: 137/255, blue: 255/255, opacity: 1) 
        let success = Color(.sRGB, red: 0/255, green: 164/255, blue: 84/255, opacity: 1) 
        let critical = Color(.sRGB, red: 210/255, green: 48/255, blue: 49/255, opacity: 1) 
        ...
    }
}
```

For borders, shadows, radii and text styles, the exporter will generate extensions that expose the tokens in a way they can be directly applied to UI elements.

```
import SwiftUI

extension Text {

    func textStyleUi11Regular() -> some View {
    return self
        .font(Font.custom("PoppinsRegular", size: 11) 
        .underline() 
        .textCase(.uppercase) 
    }
}
```


## Example Usage

Once you have run the exporter against your design system, you can start using the code in your codebase right away. Here are a few examples of how you can use the output of the [SwiftUI] exporter:

### Using a color and a text style

```
struct ContentView: View {
    var body: some View {
        Text("Styled text")
            .foregroundColor(Color.Token.primary)
            .textStyleUi11Regular()
    }
}
```

## Installing

In order to make the Supernova SwiftUI exporter available for your organization so you can start generating code from your design system, please follow the installation guide in our [developer documentation](https://developers.supernova.io/using-exporters/installing-exporters).

## Reporting Bugs or Requesting Features

In order to faciliate easy communication and speed up delivery of fixes and features for this exporter, we require everyone to log all issues and feature requests through the issue tracking of this repository. 

Please read through the [existing issues](../../issues) before you open a new issue! It might be that we have already discussed it before. If you are sure your request wasn't mentioned just yet, proceed to [open a new issue](../../issues) and fill in the required information. Thank you!

## Contributing

If you have an idea for improving this exporter package or want a specific issue fixed quickly, we would love to see you contribute to its development! 

There are multiple ways you can contribute, so we have written a [contribution guide](https://developers.supernova.io/building-exporters/contribution-and-requests) that will walk your through the process. Any pull requests to this repository are very welcome.

## License

This exporter is distributed under the [MIT license](./LICENSE.md). [We absolutely encourage you](https://developers.supernova.io/building-exporters/cloning-exporters) to clone it and modify it for your purposes, so it fits the requirements of your stack. If you see that you have created something amazing in the process that others would benefit from, we strongly recommend you consider [publishing it back to the community](https://developers.supernova.io/building-exporters/sharing-exporters-with-others) as well.

## Useful Links

- To learn more about Supernova, [go visit our website](https://supernova.io)
- To join our community of fellow developers where we try to push what is possible with design systems and code automation, join our [community discord](https://community.supernova.io)
- To understand everything you can do with Supernova and how much time and resources it can save you, go read our [product documentation](https://learn.supernova.io/)
- Finally, to learn everything about what exporters are and how you can integrate with your codebase, go read our [developer documentation](https://developers.supernova.io/)

## Other Supernova Exporters

We are developing and maintaining exporters for many major technologies. Here are all the official exporters maintained by Supernova:

- [iOS Exporter](https://github.com/Supernova-Studio/exporter-ios)
- [iOS Localization Exporter](https://github.com/Supernova-Studio/exporter-ios-localization)
- [Android Exporter](https://github.com/Supernova-Studio/exporter-android)
- [React Exporter](https://github.com/Supernova-Studio/exporter-react)
- [Flutter Exporter](https://github.com/Supernova-Studio/exporter-flutter)
- [Angular Exporter](https://github.com/Supernova-Studio/exporter-angular)
- [Typescript Exporter](https://github.com/Supernova-Studio/exporter-typescript)
- [CSS Exporter](https://github.com/Supernova-Studio/exporter-css)
- [LESS Exporter](https://github.com/Supernova-Studio/exporter-less)
- [SASS Exporter](https://github.com/Supernova-Studio/exporter-sass)


Additionally, we are also developing and maintaining exporters for specific use cases:

- [Style Dictionary Exporter](https://github.com/Supernova-Studio/exporter-style-dictionary)
- [HTML Preview Exporter](https://github.com/Supernova-Studio/exporter-html-preview)

To browse all exporters created by our amazing community, please visit the [Supernova](https://supernova.io) Exporter Store.






