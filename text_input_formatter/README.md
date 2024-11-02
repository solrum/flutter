
[![pub package](https://img.shields.io/pub/v/text_input_formatter.svg)](https://pub.dartlang.org/packages/text_input_formatter)
# Input Formatter plugin for Flutter
A Flutter package that provides customizable input formatting for text fields. Easily enforce specific patterns and separators, ensuring consistent and user-friendly text input experiences. Ideal for formatting dates, numbers, or any other structured input, this package enhances your app's data entry interface.

This package extends pattern_formatter, adding enhanced functionality for precise and flexible numeric input handling. Key features include:

	• Extended Decimal Precision: Supports up to 18 decimal digits, ensuring high accuracy for financial or scientific applications.
	• Precision Preservation with Decimal: Uses the Decimal library to prevent unintended rounding of double values.
	• Input Length Control: Limits the maximum number of input characters, ensuring consistency and avoiding overflow.
	• Original Value Extraction: Provides a method to convert formatted values back to the raw, original numeric input.
	• Locale-Specific Custom Formatting: Allows custom formatting rules based on locale, making the package versatile across regional formats.

## Getting Started
Add pubspec.yaml

```yaml
dependencies:
  currency_text_input_formatter: ^1.0.0
```

### Solving Intl package conflict
```yaml
dependency_overrides:
  intl: [your_version]
```

## Usage

```dart
import 'package:input_formatter/input_formatter.dart';
```

### Numeric Format

```dart
TextField(
    inputFormatters: [
        NumericFormatter(
            allowFraction: true,
            fractionDigits: 5,
        ),
    ],
),
```

### Date Format


```dart
TextField(
    decoration: InputDecoration(
        hintText: DatePattern.yyyy_MM_dd.value,
    ),
    inputFormatters: [
        DateFormatter(
            separator: DateSeparator.dash,
            pattern: DatePattern.yyyy_MM_dd,
        ),
    ],
)
```

### Credit Card
```dart
TextField(
    inpuFormatters: [
        CreditCardFormatter(),
    ],
)
```