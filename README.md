# Как скейлить кастомный шрифт, чтобы он поддерживал Dynamic Type

## SwiftUI

В iOS 14 или более поздних версиях, кастомные шрифты масштабируются автоматически. Для того, что бы склеить шрифт необходимо использовать символ « + »

![swiftui](https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/59e4cf04-ba8e-4bf1-a257-ced38fe3cd93)


## UIKit

В iOS 13 или более поздних версиях, для того, что бы склеить кастомные шрифты, необходимо создать NSMutableAttributedString:

```
let attributedText = NSMutableAttributedString(string: "Text custom bold", attributes: [.font: boldFont, .foregroundColor: UIColor.blue])
```

После, используйте свойство .append для добавления шрифта:

```
attributedText.append(NSAttributedString(string: "Text custom medium", attributes: [.font: mediumFont, .foregroundColor: UIColor.blue]))
```

Что бы сделать шрифт масштабируемым, создайте UIFontMetrics с использованием кастомного шрифта и размера:

```
    private func scaledFont(name: String, size: CGFloat) -> UIFont {
        let textStyle = UIFont.TextStyle.body
        let font = UIFont(name: name, size: size) ?? UIFont.systemFont(ofSize: size)
        let metrics = UIFontMetrics(forTextStyle: textStyle)
        
        return metrics.scaledFont(for: font)
    }
```

Код полностью:

![uikit](https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/231a1919-d0ed-42ea-95e5-b98cc92f3a7f)


