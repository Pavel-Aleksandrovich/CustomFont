# Как скейлить кастомный шрифт, чтобы он поддерживал Dynamic Type

## SwiftUI

В iOS 14 или более поздних версиях, кастомные шрифты масштабируются автоматически:

![SwiftUI](https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/d3f743a1-6591-4c20-9902-ade4bfec4ce7)

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

![UIKit](https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/2e1fd752-880a-4108-8b6e-7d9513c297bb)

https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/1a15aaf6-3e23-4a52-a4ed-2c3a0af6703f
