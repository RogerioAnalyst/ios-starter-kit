# NSAttributedString

## Paragraph Spacing

<img src="https://github.com/jrasmusson/ios-starter-kit/blob/master/basics/NSAttributedString/images/paragraph.png" width="400"/>

```swift
    let nameLabel: UILabel = {
        let label = UILabel()
        label.numberOfLines = 2
        
        label.translatesAutoresizingMaskIntoConstraints = false
        
        let attributedText = NSMutableAttributedString(string: "Kevin Flynn", attributes: [NSAttributedString.Key.font: UIFont.boldSystemFont(ofSize: 14)])
        attributedText.append(NSAttributedString(string: "\nFebruary 10 • San Francisco ", attributes: [NSAttributedString.Key.font: UIFont.systemFont(ofSize: 12), NSAttributedString.Key.foregroundColor: UIColor.gray]))
        
        let paragraphStyle = NSMutableParagraphStyle()
        paragraphStyle.lineSpacing = 4
        attributedText.addAttribute(NSAttributedString.Key.paragraphStyle, value: paragraphStyle, range: NSMakeRange(0, attributedText.string.count))
        
        // check mark
        let attachment = NSTextAttachment()
        attachment.image = UIImage(named: "globe_icon")
        attachment.bounds = CGRect(x: 0, y: -2, width: 16, height: 16)
        attributedText.append(NSAttributedString(attachment: attachment))
        
        label.attributedText = attributedText
        return label
        
    }()
```

### Paragraph style

```swift
let paragraphStyle = NSMutableParagraphStyle()
paragraphStyle.lineSpacing = 4
attributedText.addAttribute(NSAttributedString.Key.paragraphStyle, value: paragraphStyle, range: NSMakeRange(0, attributedText.string.count))
```
## Others

```swift
let attributedText = NSMutableAttributedString(string: "Kevin Flynn", attributes: [
    NSAttributedString.Key.font: UIFont.boldSystemFont(ofSize: 16),
    NSAttributedString.Key.kern: 1
    ])
```