# Как скейлить кастомный шрифт, чтобы он поддерживал Dynamic Type

## SwiftUI

В iOS 14 или более поздних версиях, кастомные шрифты масштабируются автоматически:

![SwiftUI](https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/04af8aab-08a6-41b3-af8e-75cb569edbdc)

## UIKit

В iOS 13 или более поздних версиях, для поддержки Dynamic Type необходимо использовать объект класса UIFontMetrics:

```
private func scaledFont(_ customFont: UIFont) -> UIFont {
    
    // Создали объект UIFontMetrics, который определяет стиль шрифта — например, body или title
    let fontMetrics = UIFontMetrics(forTextStyle: .body)
    
    // Получаем UIFont, который автоматически масштабируется
    return fontMetrics.scaledFont(for: customFont)
}
```

А так же, разрешим автоматическое обновление шрифта при изменении размера:

```
textLabel.adjustsFontForContentSizeCategory = true
```

Код полностью:

![UIKit](https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/dd89cc21-34c1-48bb-84f6-11c19368b798)


