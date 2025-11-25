# 📝 Episode 08: UniformGrid - Quick Reference

> **Problem**: Grid requires row/column definitions. What if you want **all cells the same size**?
> 
> **Solution**: **UniformGrid** - Automatic equal-sized cells!

---

## 🎯 The Problem UniformGrid Solves

### Scenario: Photo Gallery

You're building a **photo gallery** where all photos should have the same size:

```xml
<!-- ❌ Grid: Too much code for equal cells -->
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*"/>
        <RowDefinition Height="*"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    
    <Image Grid.Row="0" Grid.Column="0" Source="photo1.jpg"/>
    <Image Grid.Row="0" Grid.Column="1" Source="photo2.jpg"/>
    <Image Grid.Row="0" Grid.Column="2" Source="photo3.jpg"/>
    <Image Grid.Row="1" Grid.Column="0" Source="photo4.jpg"/>
    <Image Grid.Row="1" Grid.Column="1" Source="photo5.jpg"/>
    <Image Grid.Row="1" Grid.Column="2" Source="photo6.jpg"/>
    <!-- Must specify Grid.Row and Grid.Column for EVERY item! -->
</Grid>
```

**Problems:**
- ❌ **Too much code** - Row/Column definitions, Grid.Row/Grid.Column for every element
- ❌ **Tedious** - Must specify position for each element
- ❌ **Error-prone** - Easy to forget or misplace indices

### UniformGrid Solution

```xml
<UniformGrid Rows="3" Columns="3">
    <Image Source="photo1.jpg"/>
    <Image Source="photo2.jpg"/>
    <Image Source="photo3.jpg"/>
    <Image Source="photo4.jpg"/>
    <Image Source="photo5.jpg"/>
    <Image Source="photo6.jpg"/>
    <Image Source="photo7.jpg"/>
    <Image Source="photo8.jpg"/>
    <Image Source="photo9.jpg"/>
</UniformGrid>
```

**Benefits:**
- ✅ **Short code** - No position specifications
- ✅ **All cells equal size** - Automatically enforced
- ✅ **Auto-arranged** - Elements placed sequentially
- ✅ **Perfect for galleries** - Icons, photos, products

---

## 📚 UniformGrid Basics

### What is UniformGrid?

**UniformGrid** = Grid where **all cells have equal size**

**Key differences from Grid:**

| Feature | Grid | UniformGrid |
|---------|------|-------------|
| **Cell Size** | Different sizes | All equal |
| **Position** | Manual (Grid.Row/Column) | Automatic (sequential) |
| **Definitions** | Required | Not needed |
| **Use Case** | Complex layouts | Equal-sized grids |

### Basic Usage

```xml
<UniformGrid Rows="2" Columns="2">
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
</UniformGrid>
```

**Result:**
```
┌────────┬────────┐
│   1    │   2    │  ← All cells same size
├────────┼────────┤
│   3    │   4    │
└────────┴────────┘
```

**Elements placed automatically:**
- Element 1 → Row 0, Column 0
- Element 2 → Row 0, Column 1
- Element 3 → Row 1, Column 0
- Element 4 → Row 1, Column 1

---

## 🧭 UniformGrid Properties

### Rows and Columns

Specify grid dimensions:

```xml
<UniformGrid Rows="3" Columns="2">
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
    <Button Content="5"/>
    <Button Content="6"/>
</UniformGrid>
```

**Result:** 3 rows × 2 columns = 6 cells

**Visual:**
```
┌──────┬──────┐
│  1   │  2   │
├──────┼──────┤
│  3   │  4   │
├──────┼──────┤
│  5   │  6   │
└──────┴──────┘
```

### Auto-Calculate Rows or Columns

**Specify only Columns** - Rows calculated automatically:

```xml
<UniformGrid Columns="3">
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
    <Button Content="5"/>
    <Button Content="6"/>
</UniformGrid>
```

**Result:** 6 elements ÷ 3 columns = **2 rows** (automatic!)

**Specify only Rows** - Columns calculated automatically:

```xml
<UniformGrid Rows="2">
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
    <Button Content="5"/>
    <Button Content="6"/>
</UniformGrid>
```

**Result:** 6 elements ÷ 2 rows = **3 columns** (automatic!)

### No Specification

**Neither Rows nor Columns** - Both calculated:

```xml
<UniformGrid>
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
</UniformGrid>
```

**Result:** Creates smallest square grid (2×2 for 4 elements)

### FirstColumn Property

Start elements from specific column (0-indexed):

```xml
<UniformGrid Rows="2" Columns="3" FirstColumn="1">
    <Button Content="A"/>
    <Button Content="B"/>
    <Button Content="C"/>
    <Button Content="D"/>
</UniformGrid>
```

**Result:**
```
┌────────┬────────┬────────┐
│ Empty  │   A    │   B    │  ← Starts from column 1
├────────┼────────┼────────┤
│   C    │   D    │ Empty  │
└────────┴────────┴────────┘
```

**Use case:** Rarely needed, useful for special layouts

---

## 💡 Common Patterns

### Pattern 1: Photo Gallery (3×3)

```xml
<UniformGrid Rows="3" Columns="3" Margin="10">
    <Border Background="Red" Margin="5">
        <Image Source="photo1.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Orange" Margin="5">
        <Image Source="photo2.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Yellow" Margin="5">
        <Image Source="photo3.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Green" Margin="5">
        <Image Source="photo4.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Blue" Margin="5">
        <Image Source="photo5.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Purple" Margin="5">
        <Image Source="photo6.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Pink" Margin="5">
        <Image Source="photo7.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Brown" Margin="5">
        <Image Source="photo8.jpg" Stretch="UniformToFill"/>
    </Border>
    <Border Background="Gray" Margin="5">
        <Image Source="photo9.jpg" Stretch="UniformToFill"/>
    </Border>
</UniformGrid>
```

### Pattern 2: Icon Grid (4×4)

```xml
<UniformGrid Rows="4" Columns="4" Margin="10">
    <Button Content="📁" FontSize="32" Margin="5"/>
    <Button Content="📄" FontSize="32" Margin="5"/>
    <Button Content="📷" FontSize="32" Margin="5"/>
    <Button Content="🎵" FontSize="32" Margin="5"/>
    <Button Content="🎬" FontSize="32" Margin="5"/>
    <Button Content="📧" FontSize="32" Margin="5"/>
    <Button Content="⚙️" FontSize="32" Margin="5"/>
    <Button Content="🔍" FontSize="32" Margin="5"/>
    <Button Content="💾" FontSize="32" Margin="5"/>
    <Button Content="🖨️" FontSize="32" Margin="5"/>
    <Button Content="📊" FontSize="32" Margin="5"/>
    <Button Content="📈" FontSize="32" Margin="5"/>
    <Button Content="🌐" FontSize="32" Margin="5"/>
    <Button Content="📱" FontSize="32" Margin="5"/>
    <Button Content="💻" FontSize="32" Margin="5"/>
    <Button Content="🖥️" FontSize="32" Margin="5"/>
</UniformGrid>
```

### Pattern 3: Calculator (4×4)

```xml
<UniformGrid Rows="4" Columns="4" Margin="10">
    <!-- Row 1 -->
    <Button Content="7" FontSize="24" Margin="2"/>
    <Button Content="8" FontSize="24" Margin="2"/>
    <Button Content="9" FontSize="24" Margin="2"/>
    <Button Content="/" FontSize="24" Margin="2" Background="LightBlue"/>
    
    <!-- Row 2 -->
    <Button Content="4" FontSize="24" Margin="2"/>
    <Button Content="5" FontSize="24" Margin="2"/>
    <Button Content="6" FontSize="24" Margin="2"/>
    <Button Content="*" FontSize="24" Margin="2" Background="LightBlue"/>
    
    <!-- Row 3 -->
    <Button Content="1" FontSize="24" Margin="2"/>
    <Button Content="2" FontSize="24" Margin="2"/>
    <Button Content="3" FontSize="24" Margin="2"/>
    <Button Content="-" FontSize="24" Margin="2" Background="LightBlue"/>
    
    <!-- Row 4 -->
    <Button Content="0" FontSize="24" Margin="2"/>
    <Button Content="." FontSize="24" Margin="2"/>
    <Button Content="=" FontSize="24" Margin="2" Background="Orange"/>
    <Button Content="+" FontSize="24" Margin="2" Background="LightBlue"/>
</UniformGrid>
```

### Pattern 4: Color Picker

```xml
<UniformGrid Rows="4" Columns="6" Margin="10">
    <Border Background="#FF0000" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FF6600" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FFCC00" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#00FF00" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#0099FF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#6633FF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    
    <Border Background="#FF3333" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FF9933" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FFFF33" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#33FF33" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#33CCFF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#9966FF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    
    <Border Background="#FF6666" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FFCC66" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FFFF66" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#66FF66" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#66FFFF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#CC99FF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    
    <Border Background="#FF9999" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FFCC99" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FFFF99" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#99FF99" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#99FFFF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
    <Border Background="#FFCCFF" Margin="2" Height="40" Width="40" Cursor="Hand"/>
</UniformGrid>
```

### Pattern 5: Product Grid

```xml
<UniformGrid Columns="4" Margin="10">
    <Border BorderBrush="Gray" BorderThickness="1" Margin="5" Padding="10">
        <StackPanel>
            <Image Source="product1.jpg" Height="150" Stretch="Uniform"/>
            <TextBlock Text="Product 1" FontWeight="Bold" Margin="0,5" TextAlignment="Center"/>
            <TextBlock Text="$19.99" Foreground="Green" FontSize="16" TextAlignment="Center"/>
            <Button Content="Add to Cart" Margin="0,5"/>
        </StackPanel>
    </Border>
    
    <Border BorderBrush="Gray" BorderThickness="1" Margin="5" Padding="10">
        <StackPanel>
            <Image Source="product2.jpg" Height="150" Stretch="Uniform"/>
            <TextBlock Text="Product 2" FontWeight="Bold" Margin="0,5" TextAlignment="Center"/>
            <TextBlock Text="$29.99" Foreground="Green" FontSize="16" TextAlignment="Center"/>
            <Button Content="Add to Cart" Margin="0,5"/>
        </StackPanel>
    </Border>
    
    <!-- More products... -->
</UniformGrid>
```

### Pattern 6: Dashboard Widgets (2×2)

```xml
<UniformGrid Rows="2" Columns="2" Margin="20">
    <Border Background="LightBlue" Margin="10" Padding="20" CornerRadius="10">
        <StackPanel>
            <TextBlock Text="💰 Sales" FontSize="20" FontWeight="Bold" Margin="0,0,0,10"/>
            <TextBlock Text="$12,345" FontSize="36" FontWeight="Bold"/>
            <TextBlock Text="+12% from last month" Foreground="Green" Margin="0,5,0,0"/>
        </StackPanel>
    </Border>
    
    <Border Background="LightGreen" Margin="10" Padding="20" CornerRadius="10">
        <StackPanel>
            <TextBlock Text="👥 Users" FontSize="20" FontWeight="Bold" Margin="0,0,0,10"/>
            <TextBlock Text="1,234" FontSize="36" FontWeight="Bold"/>
            <TextBlock Text="+5% from last month" Foreground="Green" Margin="0,5,0,0"/>
        </StackPanel>
    </Border>
    
    <Border Background="LightCoral" Margin="10" Padding="20" CornerRadius="10">
        <StackPanel>
            <TextBlock Text="📦 Orders" FontSize="20" FontWeight="Bold" Margin="0,0,0,10"/>
            <TextBlock Text="456" FontSize="36" FontWeight="Bold"/>
            <TextBlock Text="+8% from last month" Foreground="Green" Margin="0,5,0,0"/>
        </StackPanel>
    </Border>
    
    <Border Background="LightGoldenrodYellow" Margin="10" Padding="20" CornerRadius="10">
        <StackPanel>
            <TextBlock Text="💵 Revenue" FontSize="20" FontWeight="Bold" Margin="0,0,0,10"/>
            <TextBlock Text="$45,678" FontSize="36" FontWeight="Bold"/>
            <TextBlock Text="+15% from last month" Foreground="Green" Margin="0,5,0,0"/>
        </StackPanel>
    </Border>
</UniformGrid>
```

---

## ⚖️ UniformGrid vs Grid

### When to Use UniformGrid

✅ **Use UniformGrid when:**
- All cells should be **same size**
- Elements are **similar type** (photos, icons, buttons)
- **No need for spanning** (RowSpan, ColumnSpan)
- **Simple, equal layout** required

**Perfect for:**
- Photo galleries
- Icon grids
- Calculators
- Product catalogs
- Dashboard widgets
- Color pickers

**Example:**
```xml
<UniformGrid Rows="3" Columns="3">
    <Image Source="photo1.jpg"/>
    <Image Source="photo2.jpg"/>
    <!-- All photos same size -->
</UniformGrid>
```

### When to Use Grid

✅ **Use Grid when:**
- Cells need **different sizes**
- Need **proportional sizing** (Star *)
- Need **spanning** (RowSpan, ColumnSpan)
- **Complex layouts** with varying content

**Perfect for:**
- Form layouts
- Application UI
- Complex page layouts
- Different-sized elements

**Example:**
```xml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="Auto"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    <TextBlock Grid.Column="0" Text="Name:"/>
    <TextBox Grid.Column="1"/>
    <!-- Different column sizes -->
</Grid>
```

### Comparison Table

| Feature | UniformGrid | Grid |
|---------|-------------|------|
| **Cell Size** | All equal | Different sizes |
| **Position** | Automatic | Manual (Grid.Row/Column) |
| **Definitions** | Not needed | Required |
| **Spanning** | ❌ Not supported | ✅ Supported |
| **Proportional** | ❌ No | ✅ Yes (Star *) |
| **Code Length** | ✅ Short | ⚠️ Longer |
| **Use Case** | Equal grids | Complex layouts |
| **Performance** | ✅ Faster | ⚡ Good |

---

## ⚠️ Common Problems & Solutions

### Problem 1: Trying Different Cell Sizes

```xml
<!-- ❌ Problem: Trying to make cells different sizes -->
<UniformGrid Rows="2" Columns="2">
    <Button Content="Big" Width="200" Height="200"/>
    <Button Content="Small" Width="50" Height="50"/>
    <!-- Width/Height ignored! All cells still equal! -->
</UniformGrid>

<!-- ✅ Solution: Use Grid instead -->
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="2*"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="2*"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    <Button Grid.Row="0" Grid.Column="0" Content="Big"/>
    <Button Grid.Row="1" Grid.Column="1" Content="Small"/>
</Grid>
```

### Problem 2: Using for Form Layouts

```xml
<!-- ❌ Bad: UniformGrid for forms (labels and inputs different sizes) -->
<UniformGrid Rows="3" Columns="2">
    <TextBlock Text="Name:"/>      <!-- Should be narrow -->
    <TextBox/>                      <!-- Should be wide -->
    <TextBlock Text="Email:"/>
    <TextBox/>
    <TextBlock Text="Password:"/>
    <TextBox/>
    <!-- All cells same size = awkward form -->
</UniformGrid>

<!-- ✅ Good: Use Grid with Auto and * -->
<Grid Margin="10">
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="Auto"/>
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="Auto"/>  <!-- Label: Auto width -->
        <ColumnDefinition Width="*"/>     <!-- Input: Fill remaining -->
    </Grid.ColumnDefinitions>
    
    <TextBlock Grid.Row="0" Grid.Column="0" Text="Name:" Margin="5"/>
    <TextBox Grid.Row="0" Grid.Column="1" Margin="5"/>
    <TextBlock Grid.Row="1" Grid.Column="0" Text="Email:" Margin="5"/>
    <TextBox Grid.Row="1" Grid.Column="1" Margin="5"/>
    <TextBlock Grid.Row="2" Grid.Column="0" Text="Password:" Margin="5"/>
    <PasswordBox Grid.Row="2" Grid.Column="1" Margin="5"/>
</Grid>
```

### Problem 3: Too Many/Few Elements

```xml
<!-- ❌ Problem: 5 elements in 2×2 grid (4 cells) -->
<UniformGrid Rows="2" Columns="2">
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
    <Button Content="5"/>  <!-- No space! Will create extra row -->
</UniformGrid>

<!-- ✅ Solution 1: Adjust grid size -->
<UniformGrid Rows="2" Columns="3">
    <!-- Now 6 cells for 5 elements -->
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
    <Button Content="5"/>
</UniformGrid>

<!-- ✅ Solution 2: Use auto-calculate -->
<UniformGrid Columns="3">
    <!-- Automatically creates 2 rows for 5 elements -->
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
    <Button Content="5"/>
</UniformGrid>
```

### Problem 4: Need Spanning

```xml
<!-- ❌ UniformGrid doesn't support spanning -->
<UniformGrid Rows="2" Columns="2">
    <Button Content="Span 2 cols?"/>  <!-- Can't span! -->
    <Button Content="2"/>
    <Button Content="3"/>
</UniformGrid>

<!-- ✅ Use Grid with spanning -->
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
        <ColumnDefinition/>
        <ColumnDefinition/>
    </Grid.ColumnDefinitions>
    
    <Button Grid.Row="0" Grid.Column="0" Grid.ColumnSpan="2" Content="Spans 2 cols"/>
    <Button Grid.Row="1" Grid.Column="0" Content="3"/>
    <Button Grid.Row="1" Grid.Column="1" Content="4"/>
</Grid>
```

---

## 💪 Best Practices

### Do's ✅

1. **Use for equal-sized elements**
   ```xml
   <UniformGrid Rows="3" Columns="3">
       <!-- Perfect for photo gallery -->
   </UniformGrid>
   ```

2. **Let it auto-calculate**
   ```xml
   <UniformGrid Columns="4">
       <!-- Rows calculated automatically -->
   </UniformGrid>
   ```

3. **Use Margin for spacing**
   ```xml
   <UniformGrid Rows="2" Columns="2">
       <Button Margin="5"/>
       <Button Margin="5"/>
   </UniformGrid>
   ```

4. **Perfect for icons, photos, buttons**
   ```xml
   <UniformGrid Columns="5">
       <Button Content="🏠"/>
       <Button Content="📁"/>
       <!-- Icon toolbar -->
   </UniformGrid>
   ```

### Don'ts ❌

1. **Don't use for forms**
   - Labels and inputs need different sizes
   - Use Grid instead

2. **Don't try to make cells different sizes**
   - UniformGrid enforces equal sizes
   - Use Grid if you need different sizes

3. **Don't use when spanning needed**
   - UniformGrid doesn't support RowSpan/ColumnSpan
   - Use Grid instead

4. **Don't forget element count**
   - Ensure elements fit in grid (Rows × Columns)
   - Or use auto-calculate

---

## 📋 Quick Reference

### UniformGrid Properties

```xml
<UniformGrid Rows="3"           <!-- Number of rows -->
             Columns="4"        <!-- Number of columns -->
             FirstColumn="0">   <!-- Starting column (0-indexed) -->
</UniformGrid>
```

### Auto-Calculate Options

```xml
<!-- Option 1: Specify Columns, auto-calculate Rows -->
<UniformGrid Columns="4">
    <!-- 12 elements = 3 rows automatically -->
</UniformGrid>

<!-- Option 2: Specify Rows, auto-calculate Columns -->
<UniformGrid Rows="3">
    <!-- 12 elements = 4 columns automatically -->
</UniformGrid>

<!-- Option 3: Specify neither, auto-calculate both -->
<UniformGrid>
    <!-- Creates smallest square grid -->
</UniformGrid>
```

### Common Use Cases

| Use Case | Rows | Columns | Example |
|----------|------|---------|---------|
| Photo Gallery | 3 | 3 | Instagram-style grid |
| Calculator | 4-5 | 4 | Number pad + operators |
| Icon Grid | 4 | 4 | Application launcher |
| Color Picker | 4-6 | 6-8 | Color palette |
| Dashboard | 2 | 2-3 | KPI widgets |
| Product Grid | Auto | 3-4 | E-commerce catalog |

---

## 🎯 Summary

**UniformGrid** is perfect for **equal-sized grids**:

| Aspect | Description |
|--------|-------------|
| **Purpose** | Equal-sized cells in a grid |
| **Positioning** | Automatic (sequential) |
| **Layout** | All cells same size |
| **Best For** | Photos, icons, buttons, products |
| **Avoid For** | Forms, complex layouts, different sizes |
| **Key Properties** | Rows, Columns, FirstColumn |
| **Code** | ✅ Very short and clean |

**When to use:**
- ✅ Photo galleries
- ✅ Icon grids
- ✅ Calculators
- ✅ Dashboard widgets
- ✅ Product catalogs
- ✅ Color pickers

**When NOT to use:**
- ❌ Forms (different-sized fields)
- ❌ Need cell spanning
- ❌ Need proportional sizing
- ❌ Complex layouts

---

## 🔗 Related

- **Alternative**: [Episode 04 - Grid](../WPF_Episode04_Grid) - For complex layouts
- **Previous**: [Episode 07 - Canvas](../WPF_Episode07_Canvas) - Absolute positioning
- **Next**: [Episode 09 - ScrollViewer](../WPF_Episode09_ScrollView) - Scrollable content

---

*For complete examples, see [README.md](README.md)*
