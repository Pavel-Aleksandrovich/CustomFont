# Как скейлить кастомный шрифт, чтобы он поддерживал Dynamic Type

## SwiftUI

В iOS 14 или более поздних версиях, кастомные шрифты масштабируются автоматически:





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

Код полночтью:




