# GlobalPhoneAreaCodeKit

A Swift Package for querying global phone area codes, identifying regions, and resolving location data from phone numbers.

This library parses comprehensive CSV data into an easy-to-use Swift API, allowing you to look up area codes, search for cities, and filter by country.

## Installation

### Swift Package Manager

Add the following to your `Package.swift` file:

```swift
dependencies: [
    .package(url: "https://github.com/GlobalPhoneAreaCodes/GlobalPhoneAreaCodeKit.git", from: "1.0.0")
]
```

## Usage

```swift
import GlobalPhoneAreaCodeKit

// 1. Lookup specific code
let codes = GlobalPhoneAreaCodeKit.shared.lookup(code: "212")
if let nyc = codes.first {
    print(nyc.region) // "NY"
    print(nyc.city)   // "Manhattan"
    print(nyc.flag)   // "🇺🇸"
}

// 2. Search by text (City, Region, or Notes)
let results = GlobalPhoneAreaCodeKit.shared.search("Paris")
// Returns entries for Paris, France (331) etc.

// 3. Filter by Country
let canadianCodes = GlobalPhoneAreaCodeKit.shared.codes(forCountry: "Canada")
```

## Supported Countries / Regions

The library currently includes data for the following:

| Code | Country |
|------|---------|
| AD | Andorra 🇦🇩 |
| AL | Albania 🇦🇱 |
| AT | Austria 🇦🇹 |
| BA | Bosnia and Herzegovina 🇧🇦 |
| BE | Belgium 🇧🇪 |
| BG | Bulgaria 🇧🇬 |
| BR | Brazil 🇧🇷 |
| BY | Belarus 🇧🇾 |
| CA | Canada 🇨🇦 |
| CH | Switzerland 🇨🇭 |
| CZ | Czech Republic 🇨🇿 |
| DE | Germany 🇩🇪 |
| FR | France 🇫🇷 |
| GB | United Kingdom 🇬🇧 |
| GG | Guernsey 🇬🇬 |
| GI | Gibraltar 🇬🇮 |
| GR | Greece 🇬🇷 |
| HR | Croatia 🇭🇷 |
| HU | Hungary 🇭🇺 |
| MX | Mexico 🇲🇽 |
| US | United States 🇺🇸 |

## Data Sources & Origin

This repository started as a collection of CSVs to map phone numbers to locations. It addresses the difficulty of finding accurate, free area code data compared to zip codes.

- **US**: NANPA (North American Numbering Plan)
- **Canada**: CNAC (Canadian Numbering Administrator)
- **Geolocation**: Geonames
- **European/Other**: Compiled from public numbering plans.

## License

You are free to use this compilation for any purpose (commercial or not).
