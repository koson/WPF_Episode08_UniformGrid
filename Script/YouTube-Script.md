# สคริปต์การสอน: WPF Episode 08 - UniformGrid

## เนื้อหาที่จะสอน

### 1. UniformGrid คืออะไร
- Panel ที่สร้าง Grid โดยทุก Cell มีขนาดเท่ากันหมด
- เหมาะสำหรับ Photo Gallery, Icon Grid, Button Grid

### 2. UniformGrid Properties
- Rows - จำนวนแถว
- Columns - จำนวนคอลัมน์
- FirstColumn - เริ่มที่คอลัมน์ไหน

### 3. การใช้งาน
- Photo Gallery
- Icon Grid
- Button Grid
- Calculator Layout

---

## ส่วนที่ 1: Introduction (0:00 - 2:00)

**สวัสดีครับทุกคน**

ยินดีต้อนรับกลับมาสู่ WPF Tutorial Series ของเรา

วันนี้เราจะมาเรียนรู้เกี่ยวกับ **UniformGrid** ซึ่งเป็น Panel ที่น่าสนใจมาก!

จำ Grid ที่เราเรียนในตอนที่แล้วได้ไหมครับ? Grid สามารถกำหนดขนาดแต่ละ Row/Column ได้ต่างกัน

แต่ **UniformGrid ต่างครับ!**

UniformGrid จะสร้าง Grid ที่ **ทุก Cell มีขนาดเท่ากันหมด!**

เหมาะมากสำหรับ Photo Gallery, Icon Grid, Calculator!

---

## ส่วนที่ 2: UniformGrid พื้นฐาน (2:00 - 6:00)

### Demo 2.1: UniformGrid ง่ายๆ

```xml
<UniformGrid Rows="2" Columns="2">
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
</UniformGrid>
```

**อธิบาย:**
- `Rows="2"` - 2 แถว
- `Columns="2"` - 2 คอลัมน์
- รวม 4 Cells (2x2)
- ทุก Cell ขนาดเท่ากันหมด!

### Demo 2.2: เปรียบเทียบกับ Grid

**Grid ธรรมดา:**
```xml
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    
    <Button Grid.Row="0" Grid.Column="0" Content="1"/>
    <Button Grid.Row="0" Grid.Column="1" Content="2"/>
    <Button Grid.Row="1" Grid.Column="0" Content="3"/>
    <Button Grid.Row="1" Grid.Column="1" Content="4"/>
</Grid>
```

**UniformGrid:**
```xml
<UniformGrid Rows="2" Columns="2">
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
</UniformGrid>
```

**เห็นไหมครับ:**
- UniformGrid สั้นกว่ามาก!
- ไม่ต้องกำหนด Grid.Row, Grid.Column
- Element เรียงตามลำดับอัตโนมัติ

---

## ส่วนที่ 3: Rows และ Columns (6:00 - 10:00)

### Demo 3.1: กำหนด Rows

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

**3 แถว x 2 คอลัมน์ = 6 Cells**

### Demo 3.2: Auto Calculate

ถ้าไม่กำหนด Rows หรือ Columns จะคำนวณอัตโนมัติ!

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

**มี 6 Elements, Columns=3**
- จะสร้าง 2 แถวโดยอัตโนมัติ!

### Demo 3.3: ไม่กำหนดอะไรเลย

```xml
<UniformGrid>
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
</UniformGrid>
```

จะสร้าง 2x2 Grid โดยอัตโนมัติ!

---

## ส่วนที่ 4: Photo Gallery Example (10:00 - 15:00)

### Demo 4.1: 3x3 Photo Gallery

นี่คือตัวอย่างจริงๆ ที่เหมาะกับ UniformGrid!

```xml
<UniformGrid Rows="3" Columns="3" Margin="20">
    <Border Background="Red" Margin="5">
        <TextBlock Text="Photo 1" FontSize="20" Foreground="White" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Orange" Margin="5">
        <TextBlock Text="Photo 2" FontSize="20" Foreground="White" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Yellow" Margin="5">
        <TextBlock Text="Photo 3" FontSize="20" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Green" Margin="5">
        <TextBlock Text="Photo 4" FontSize="20" Foreground="White" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Blue" Margin="5">
        <TextBlock Text="Photo 5" FontSize="20" Foreground="White" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Purple" Margin="5">
        <TextBlock Text="Photo 6" FontSize="20" Foreground="White" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Pink" Margin="5">
        <TextBlock Text="Photo 7" FontSize="20" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Brown" Margin="5">
        <TextBlock Text="Photo 8" FontSize="20" Foreground="White" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
    <Border Background="Gray" Margin="5">
        <TextBlock Text="Photo 9" FontSize="20" Foreground="White" 
                   HorizontalAlignment="Center" VerticalAlignment="Center"/>
    </Border>
</UniformGrid>
```

**ดีอย่างไร:**
- ทุกรูปมีขนาดเท่ากันหมด
- เรียงสวยงาม เป็นระเบียบ
- Responsive - ขนาด Cell ปรับตาม Window

### Demo 4.2: Icon Grid (4x4)

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

เหมาะมากสำหรับ Icon Menu หรือ Launcher!

---

## ส่วนที่ 5: Calculator Example (15:00 - 20:00)

### Demo 5.1: Simple Calculator Layout

UniformGrid เหมาะมากสำหรับ Calculator!

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

**ดีอย่างไร:**
- ทุกปุ่มขนาดเท่ากัน
- เหมือน Calculator จริงๆ
- Code สั้น อ่านง่าย

### Demo 5.2: Complete Calculator UI

```xml
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    
    <!-- Display -->
    <TextBlock Grid.Row="0" Text="0" 
               FontSize="48" 
               HorizontalAlignment="Right" 
               Margin="10" 
               Background="Black" 
               Foreground="White" 
               Padding="10"/>
    
    <!-- Buttons -->
    <UniformGrid Grid.Row="1" Rows="5" Columns="4" Margin="10">
        <Button Content="C" FontSize="20" Margin="2" Background="Red" Foreground="White"/>
        <Button Content="CE" FontSize="20" Margin="2" Background="Red" Foreground="White"/>
        <Button Content="←" FontSize="20" Margin="2" Background="Orange" Foreground="White"/>
        <Button Content="/" FontSize="24" Margin="2" Background="LightBlue"/>
        
        <Button Content="7" FontSize="24" Margin="2"/>
        <Button Content="8" FontSize="24" Margin="2"/>
        <Button Content="9" FontSize="24" Margin="2"/>
        <Button Content="*" FontSize="24" Margin="2" Background="LightBlue"/>
        
        <Button Content="4" FontSize="24" Margin="2"/>
        <Button Content="5" FontSize="24" Margin="2"/>
        <Button Content="6" FontSize="24" Margin="2"/>
        <Button Content="-" FontSize="24" Margin="2" Background="LightBlue"/>
        
        <Button Content="1" FontSize="24" Margin="2"/>
        <Button Content="2" FontSize="24" Margin="2"/>
        <Button Content="3" FontSize="24" Margin="2"/>
        <Button Content="+" FontSize="24" Margin="2" Background="LightBlue"/>
        
        <Button Content="0" FontSize="24" Margin="2"/>
        <Button Content="." FontSize="24" Margin="2"/>
        <Button Content="%" FontSize="24" Margin="2"/>
        <Button Content="=" FontSize="24" Margin="2" Background="Orange" Foreground="White"/>
    </UniformGrid>
</Grid>
```

---

## ส่วนที่ 6: FirstColumn Property (20:00 - 23:00)

### Demo 6.1: FirstColumn

FirstColumn ใช้สำหรับเริ่มที่คอลัมน์ไหน

```xml
<UniformGrid Rows="2" Columns="3" FirstColumn="1">
    <Button Content="A"/>
    <Button Content="B"/>
    <Button Content="C"/>
    <Button Content="D"/>
</UniformGrid>
```

**ผลลัพธ์:**
```
[Empty] [ A ] [ B ]
[ C ]   [ D ] [Empty]
```

เริ่มที่คอลัมน์ 1 (0-indexed)

### Demo 6.2: ตัวอย่างการใช้งาน

```xml
<UniformGrid Rows="3" Columns="3" FirstColumn="1">
    <Button Content="Start"/>
    <Button Content="2"/>
    <Button Content="3"/>
    <Button Content="4"/>
    <Button Content="5"/>
    <Button Content="6"/>
</UniformGrid>
```

Cell แรกจะเว้นไว้!

---

## ส่วนที่ 7: UniformGrid vs Grid (23:00 - 27:00)

### เมื่อไหร่ควรใช้ UniformGrid vs Grid?

**ใช้ UniformGrid เมื่อ:**
- ต้องการ Cell ขนาดเท่ากันหมด
- Photo Gallery
- Icon Grid
- Calculator, Keypad
- Product Grid
- Color Picker

**ใช้ Grid เมื่อ:**
- ต้องการ Row/Column ขนาดต่างกัน
- Form Layout ที่ซับซ้อน
- ต้องการควบคุม Span
- Layout ที่มีหลายระดับ

### ตัวอย่างเปรียบเทียบ

**UniformGrid - Photo Gallery:**
```xml
<UniformGrid Rows="3" Columns="3">
    <Image Source="photo1.jpg"/>
    <Image Source="photo2.jpg"/>
    <Image Source="photo3.jpg"/>
    <!-- ... -->
</UniformGrid>
```
✅ Code สั้น, Cell เท่ากันหมด

**Grid - Form Layout:**
```xml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="Auto"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    <TextBlock Grid.Column="0" Text="Name:"/>
    <TextBox Grid.Column="1"/>
</Grid>
```
✅ Column ขนาดต่างกัน, ยืดหยุ่น

---

## ส่วนที่ 8: Use Cases (27:00 - 33:00)

### 8.1 Color Picker

```xml
<UniformGrid Rows="4" Columns="6" Margin="10">
    <Border Background="#FF0000" Margin="2" Height="40" Width="40"/>
    <Border Background="#FF6600" Margin="2" Height="40" Width="40"/>
    <Border Background="#FFCC00" Margin="2" Height="40" Width="40"/>
    <Border Background="#00FF00" Margin="2" Height="40" Width="40"/>
    <Border Background="#0099FF" Margin="2" Height="40" Width="40"/>
    <Border Background="#6633FF" Margin="2" Height="40" Width="40"/>
    
    <Border Background="#FF3333" Margin="2" Height="40" Width="40"/>
    <Border Background="#FF9933" Margin="2" Height="40" Width="40"/>
    <Border Background="#FFFF33" Margin="2" Height="40" Width="40"/>
    <Border Background="#33FF33" Margin="2" Height="40" Width="40"/>
    <Border Background="#33CCFF" Margin="2" Height="40" Width="40"/>
    <Border Background="#9966FF" Margin="2" Height="40" Width="40"/>
    
    <Border Background="#FF6666" Margin="2" Height="40" Width="40"/>
    <Border Background="#FFCC66" Margin="2" Height="40" Width="40"/>
    <Border Background="#FFFF66" Margin="2" Height="40" Width="40"/>
    <Border Background="#66FF66" Margin="2" Height="40" Width="40"/>
    <Border Background="#66FFFF" Margin="2" Height="40" Width="40"/>
    <Border Background="#CC99FF" Margin="2" Height="40" Width="40"/>
    
    <Border Background="#FF9999" Margin="2" Height="40" Width="40"/>
    <Border Background="#FFCC99" Margin="2" Height="40" Width="40"/>
    <Border Background="#FFFF99" Margin="2" Height="40" Width="40"/>
    <Border Background="#99FF99" Margin="2" Height="40" Width="40"/>
    <Border Background="#99FFFF" Margin="2" Height="40" Width="40"/>
    <Border Background="#FFCCFF" Margin="2" Height="40" Width="40"/>
</UniformGrid>
```

### 8.2 Product Grid (E-Commerce)

```xml
<UniformGrid Columns="4" Margin="10">
    <Border BorderBrush="Gray" BorderThickness="1" Margin="5" Padding="10">
        <StackPanel>
            <Image Source="product1.jpg" Height="150" Stretch="Uniform"/>
            <TextBlock Text="Product 1" FontWeight="Bold" Margin="0,5"/>
            <TextBlock Text="$19.99" Foreground="Green"/>
        </StackPanel>
    </Border>
    
    <Border BorderBrush="Gray" BorderThickness="1" Margin="5" Padding="10">
        <StackPanel>
            <Image Source="product2.jpg" Height="150" Stretch="Uniform"/>
            <TextBlock Text="Product 2" FontWeight="Bold" Margin="0,5"/>
            <TextBlock Text="$29.99" Foreground="Green"/>
        </StackPanel>
    </Border>
    
    <!-- More products... -->
</UniformGrid>
```

### 8.3 Dashboard Widgets

```xml
<UniformGrid Rows="2" Columns="2" Margin="20">
    <Border Background="LightBlue" Margin="10" Padding="20">
        <StackPanel>
            <TextBlock Text="Sales" FontSize="20" FontWeight="Bold"/>
            <TextBlock Text="$12,345" FontSize="36"/>
        </StackPanel>
    </Border>
    
    <Border Background="LightGreen" Margin="10" Padding="20">
        <StackPanel>
            <TextBlock Text="Users" FontSize="20" FontWeight="Bold"/>
            <TextBlock Text="1,234" FontSize="36"/>
        </StackPanel>
    </Border>
    
    <Border Background="LightCoral" Margin="10" Padding="20">
        <StackPanel>
            <TextBlock Text="Orders" FontSize="20" FontWeight="Bold"/>
            <TextBlock Text="456" FontSize="36"/>
        </StackPanel>
    </Border>
    
    <Border Background="LightGoldenrodYellow" Margin="10" Padding="20">
        <StackPanel>
            <TextBlock Text="Revenue" FontSize="20" FontWeight="Bold"/>
            <TextBlock Text="$45,678" FontSize="36"/>
        </StackPanel>
    </Border>
</UniformGrid>
```

---

## ส่วนที่ 9: Tips & Best Practices (33:00 - 36:00)

### 9.1 ใช้ Margin ให้ดี

```xml
<!-- ✅ ดี: ใช้ Margin ใน Child -->
<UniformGrid Rows="2" Columns="2">
    <Button Content="A" Margin="5"/>
    <Button Content="B" Margin="5"/>
    <Button Content="C" Margin="5"/>
    <Button Content="D" Margin="5"/>
</UniformGrid>

<!-- หรือใช้ Margin ที่ UniformGrid -->
<UniformGrid Rows="2" Columns="2" Margin="10">
    <Button Content="A"/>
    <Button Content="B"/>
    <Button Content="C"/>
    <Button Content="D"/>
</UniformGrid>
```

### 9.2 Auto Calculate

```xml
<!-- ✅ ดี: ให้คำนวณ Rows อัตโนมัติ -->
<UniformGrid Columns="4">
    <!-- 8 items = 2 rows automatically -->
</UniformGrid>

<!-- หรือให้คำนวณ Columns อัตโนมัติ -->
<UniformGrid Rows="2">
    <!-- 8 items = 4 columns automatically -->
</UniformGrid>
```

### 9.3 Responsive Design

```xml
<!-- UniformGrid ปรับขนาดตาม Window อัตโนมัติ -->
<UniformGrid Rows="3" Columns="3">
    <!-- ทุก Cell จะปรับขนาดเท่ากันเสมอ -->
</UniformGrid>
```

### 9.4 FirstColumn

```xml
<!-- ใช้ FirstColumn เมื่อต้องการเว้น Cell แรก -->
<UniformGrid Rows="2" Columns="3" FirstColumn="1">
    <!-- Cell [0,0] จะว่าง -->
    <Button Content="Start from [0,1]"/>
</UniformGrid>
```

---

## ส่วนที่ 10: Wrap Up และ Outro (36:00 - 38:00)

**สรุปสิ่งที่เราได้เรียนรู้วันนี้:**

1. ✅ UniformGrid = ทุก Cell ขนาดเท่ากัน
2. ✅ Rows/Columns Properties
3. ✅ Auto Calculate Rows หรือ Columns
4. ✅ FirstColumn สำหรับเริ่มต้นที่คอลัมน์อื่น
5. ✅ Use Cases: Photo Gallery, Calculator, Icon Grid
6. ✅ เปรียบเทียบกับ Grid

**UniformGrid เหมาะสำหรับ:**
- Photo Gallery (รูปภาพเท่ากันหมด)
- Icon Grid (ไอคอนเท่ากัน)
- Calculator (ปุ่มเท่ากัน)
- Product Grid (สินค้าเท่ากัน)
- Color Picker (สีเท่ากัน)
- Dashboard Widgets

**จุดเด่นของ UniformGrid:**
- Code สั้น เขียนง่าย
- ไม่ต้องกำหนด Grid.Row, Grid.Column
- Responsive โดยอัตโนมัติ
- ทุก Cell ขนาดเท่ากันเสมอ

**ในตอนต่อไป:**

เราจะมาเรียนรู้เกี่ยวกับ **ScrollViewer** ซึ่งเป็น Control สำหรับ
เลื่อนดูเนื้อหาที่ยาวเกินพื้นที่ที่มี เหมาะสำหรับ Long Text, Images, Lists!

**อย่าลืม:**
- กด Like ถ้าชอบ
- Subscribe เพื่อติดตามตอนต่อไป
- Comment บอกว่าอยากเรียนเรื่องอะไรต่อไป

**ขอบคุณที่รับชมครับ แล้วพบกันใหม่ตอนหน้า สวัสดีครับ!**

---

## เอกสารอ้างอิง

### Official Documentation
- [UniformGrid Class - Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.uniformgrid)
- [Panels Overview - Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/desktop/wpf/controls/panels-overview)

### Properties Reference
```
Rows: Int32 (จำนวนแถว)
Columns: Int32 (จำนวนคอลัมน์)
FirstColumn: Int32 (คอลัมน์เริ่มต้น, 0-indexed)
```

---

## Tips & Best Practices

1. **Uniform Cells**: ทุก Cell จะมีขนาดเท่ากันเสมอ
2. **Auto Calculate**: ถ้าไม่กำหนด Rows หรือ Columns จะคำนวณอัตโนมัติ
3. **Simple Layout**: เหมาะกับ Layout ที่ต้องการความเท่าเทียม
4. **Performance**: เร็วกว่า Grid เพราะไม่ต้องคำนวณขนาดซับซ้อน

---

## Common Mistakes (ข้อผิดพลาดที่พบบ่อย)

### ❌ ลืมว่าทุก Cell เท่ากัน
```xml
<!-- ผิด: พยายามให้ Cell มีขนาดต่างกัน -->
<UniformGrid Rows="2" Columns="2">
    <Button Content="Big" Width="200"/> <!-- ไม่ได้ผล -->
    <Button Content="Small" Width="50"/> <!-- ไม่ได้ผล -->
</UniformGrid>
```

### ✅ ถูกต้อง - ใช้ Grid แทน
```xml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="2*"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    <Button Grid.Column="0" Content="Big"/>
    <Button Grid.Column="1" Content="Small"/>
</Grid>
```

### ❌ ใช้กับ Form Layout
```xml
<!-- ผิด: UniformGrid ไม่เหมาะกับ Form -->
<UniformGrid Rows="2" Columns="2">
    <TextBlock Text="Name:"/> <!-- Label ควรเล็ก -->
    <TextBox/> <!-- TextBox ควรใหญ่กว่า -->
</UniformGrid>
```

### ✅ ถูกต้อง - ใช้ Grid
```xml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="Auto"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    <TextBlock Grid.Column="0" Text="Name:"/>
    <TextBox Grid.Column="1"/>
</Grid>
```

---

## Code Examples Repository

Source code สำหรับ Episode นี้สามารถดาวน์โหลดได้ที่:
- GitHub: [WPF_Episode08_UniformGrid](https://github.com/koson/WPF_Episode08_UniformGrid)

---

**End of Script**