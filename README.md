# Как скейлить кастомный шрифт, чтобы он поддерживал Dynamic Type

## SwiftUI

В iOS 14 или более поздних версиях, кастомные шрифты масштабируются автоматически. Для того, что бы склеить шрифт необходимо использовать символ « + »

![Screenshot 2024-03-18 at 14 55 16](https://github.com/Pavel-Aleksandrovich/CustomFont/assets/87460819/4177840a-f10f-4a94-a575-10beb18ea17d)

## UIKit

В iOS 14 или более поздних версиях, необходимо создать NSMutableAttributedString

```
let attributedText = NSMutableAttributedString(string: "Text custom bold", attributes: [.font: boldFont, .foregroundColor: UIColor.blue])
```
