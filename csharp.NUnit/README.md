# Gilded Rose Testing Strategy 🧪

## Strategic Overview

This repository implements a comprehensive testing strategy for the Gilded Rose kata, focusing on code quality, maintainability, and complete coverage of business rules.

## Project Structure 📁

```plaintext
📦 GildedRoseTests
 ┣ 📜 QualityConstants.cs    # Quality boundaries and thresholds
 ┣ 📜 ItemNames.cs           # Centralized item definitions
 ┣ 📜 TestHelper.cs          # Testing utilities and factories
 ┣ 📜 GildedRoseTests.cs     # Core test implementations
 ┗ 📜 ApprovalTests.cs       # Regression test coverage
```

## Testing Strategy 🎯

### Core Testing Principles
- Test-Driven Development (TDD)
- Comprehensive scenario coverage
- Clean code and SOLID principles
- Maintainable test architecture

### Implementation Approach

#### 1. Quality Constants
```csharp
public static class QualityConstants
{
    public const int MinQuality = 0;
    public const int MaxQuality = 50;
    public const int SulfurasQuality = 80;
}
```

#### 2. Test Categories

##### Regular Items
- Quality degradation rates
- Sell-by date transitions
- Boundary conditions

##### Special Items
- Aged Brie quality progression
- Sulfuras immutability
- Backstage passes value rules

### Test Implementation Features

#### 1. Parameterized Testing
```csharp
[TestCase(10, 20, 19, Description = "Regular item before sell date")]
[TestCase(0, 20, 18, Description = "Regular item on sell date")]
```

#### 2. Factory Patterns
```csharp
public static class ItemFactory
{
    public static Item RegularItem(int sellIn = 10, int quality = 20)
    public static Item AgedBrie(int sellIn = 10, int quality = 20)
    public static Item Sulfuras(int sellIn = 0)
}
```

## Testing Coverage Matrix

| Category | Scenarios | Coverage |
|----------|-----------|----------|
| Regular Items | Quality Decrease, Boundaries | ✅ |
| Aged Brie | Quality Increase, Max Limit | ✅ |
| Sulfuras | Immutability, Consistency | ✅ |
| Backstage Passes | Time-based Rules | ✅ |


---

