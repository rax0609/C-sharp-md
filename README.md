## 1. 基本結構

### `<Window>`
- **說明**: WPF 應用程式的主要視窗容器，包含所有其他 UI 元素。
- **屬性**:
  - `x:Class`: 指定這個視窗對應的後端 C# 類別（此例為 `_2024_WpfApp3.MainWindow`）。
  - `xmlns`: 定義命名空間，用於引用不同的 XML 命名空間。
  - `Title`: 視窗的標題，此例為「飲料點餐系統ver3」。
  - `Height` 和 `Width`: 視窗的高度（620）和寬度（715）。

## 2. 命名空間（Namespaces）

- `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`: WPF 的主要命名空間，包含大部分 UI 控件。
- `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`: XAML 的基本命名空間，包含 XAML 的基本功能如 `x:Name`、`x:Class` 等。
- `xmlns:d` 和 `xmlns:mc`: 用於設計時支援（Design-Time Support）的命名空間。
- `xmlns:local="clr-namespace:_2024_WpfApp3"`: 定義本地程式集中定義的類別和控制項的命名空間。

## 3. 佈局容器

### `<Grid>`
- **說明**: 一種靈活的佈局容器，允許在行和列中排列子元素。此例中，`Grid` 作為主要佈局容器，包含所有子控制項。

## 4. 控制項解析

### 4.1. `<StackPanel x:Name="stackpanel_DrinkMenu">`
- **說明**: 用於垂直或水平排列子元素的佈局容器。此處 `StackPanel` 用於顯示飲料菜單。
- **屬性**:
  - `x:Name="stackpanel_DrinkMenu"`: 控件的名稱，便於在後端 C# 代碼中引用。
  - `Margin="20,65,0,0"`: 控制控件與其父容器邊界的距離，分別為左、上、右、下。
  - `Background="#FFF9EEEE"`: 控件的背景顏色，使用十六進位色碼。
  - `Height="505"` 和 `Width="455"`: 控件的高度和寬度。
  - `VerticalAlignment="Top"` 和 `HorizontalAlignment="Left"`: 控制控件在父容器中的對齊方式。

### 4.2. `<Button x:Name="OrderButton">`
- **說明**: 一個按鈕，用於觸發訂購操作。
- **屬性**:
  - `x:Name="OrderButton"`: 控件的名稱，便於在後端代碼中引用。
  - `Content="確定訂購"`: 按鈕上顯示的文字。
  - `Margin="0,25,30,0"`: 控制控件與其父容器邊界的距離。
  - `VerticalAlignment="Top"` 和 `HorizontalAlignment="Right"`: 控制控件在父容器中的對齊方式。
  - `Height="60"` 和 `Width="100"`: 控件的高度和寬度。
  - `FontSize="18"` 和 `FontWeight="Bold"`: 控制按鈕文字的大小和粗細。
  - `Click="OrderButton_Click"`: 定義點擊按鈕時觸發的事件處理器。

### 4.3. `<TextBlock x:Name="ResultTextBlock">`
- **說明**: 用於顯示文本內容，此處用於顯示訂單結果。
- **屬性**:
  - `x:Name="ResultTextBlock"`: 控件的名稱，便於在後端代碼中引用。
  - `Margin="490,0,20,35"`: 控制控件與其父容器邊界的距離。
  - `TextWrapping="Wrap"`: 允許文本自動換行。
  - `Background="#FFF7F3D4"`: 控件的背景顏色。
  - `Height="462"` 和 `Width`（未指定，根據 Margin 和父容器自動調整）: 控件的高度和寬度。
  - `VerticalAlignment="Bottom"`: 控制控件在父容器中的垂直對齊方式。
  - `Padding="5,5,5,5"`: 控件內部的填充距離。
  - `FontSize="16"`: 控制文本的大小。

### 4.4. `<GroupBox Header="內用/外帶">`
- **說明**: 一個分組框，用於包含相關的控制項，此處用於選擇「內用」或「外帶」。
- **屬性**:
  - `Header="內用/外帶"`: 分組框的標題。
  - `Margin="20,0,0,0"`: 控制控件與其父容器邊界的距離。
  - `Background="#FFB4F4F3"`: 控件的背景顏色。
  - `Height="52"` 和 `Width="455"`: 控件的高度和寬度。
  - `VerticalAlignment="Top"` 和 `HorizontalAlignment="Left"`: 控制控件在父容器中的對齊方式。

#### 4.4.1. `<StackPanel Orientation="Horizontal">`
- **說明**: 用於水平排列內部的 RadioButton 控件。
- **屬性**:
  - `Orientation="Horizontal"`: 控制子元素的排列方向為水平。
  - `Height="30"`: 控件的高度。

##### 4.4.1.1. `<RadioButton x:Name="DineInRadioButton">`
- **說明**: 單選按鈕，用於選擇「內用」選項。
- **屬性**:
  - `x:Name="DineInRadioButton"`: 控件的名稱，便於在後端代碼中引用。
  - `Content="內用"`: 單選按鈕旁顯示的文字。
  - `FontSize="16"` 和 `FontWeight="Bold"`: 控制文字的大小和粗細。
  - `Height="25"` 和 `Width="80"`: 控件的高度和寬度。
  - `Margin="10,0,0,0"`: 控制控件與其左側的距離。
  - `VerticalAlignment="Center"` 和 `VerticalContentAlignment="Center"`: 控制控件和內容在垂直方向上的對齊方式。
  - `GroupName="DiningOption"`: 將此 RadioButton 分組，確保在同一組內只有一個選項被選中。

##### 4.4.1.2. `<RadioButton x:Name="TakeOutRadioButton">`
- **說明**: 單選按鈕，用於選擇「外帶」選項。
- **屬性**:
  - `x:Name="TakeOutRadioButton"`: 控件的名稱，便於在後端代碼中引用。
  - `Content="外帶"`: 單選按鈕旁顯示的文字。
  - `FontSize="16"` 和 `FontWeight="Bold"`: 控制文字的大小和粗細。
  - `Height="25"` 和 `Width="80"`: 控件的高度和寬度。
  - `Margin="10,0,0,0"`: 控制控件與其左側的距離。
  - `VerticalAlignment="Center"` 和 `VerticalContentAlignment="Center"`: 控制控件和內容在垂直方向上的對齊方式。
  - `GroupName="DiningOption"`: 將此 RadioButton 分組，確保在同一組內只有一個選項被選中。

## 5. 控制項屬性詳解

### `x:Name`
- **說明**: 為 XAML 控件指定名稱，使其在後端代碼（如 C#）中可被引用和操作。例如，`x:Name="OrderButton"` 允許在 C# 中使用 `OrderButton` 來訪問此按鈕。

### `Margin`
- **說明**: 控制控件與其父容器邊界的距離，格式為 `Left, Top, Right, Bottom`。例如，`Margin="20,65,0,0"` 表示左邊距 20 像素，上邊距 65 像素，右邊距和下邊距為 0。

### `Background`
- **說明**: 控件的背景顏色，可以使用十六進位色碼或系統顏色名稱。例如，`Background="#FFF9EEEE"` 設置了一種淺粉色背景。

### `Height` 和 `Width`
- **說明**: 控制項的高度和寬度，以像素為單位。例如，`Height="60"` 和 `Width="100"` 分別設置按鈕的高度和寬度。

### `VerticalAlignment` 和 `HorizontalAlignment`
- **說明**: 控制控件在父容器中的對齊方式。
  - `VerticalAlignment`: 垂直對齊方式，如 `Top`、`Bottom`、`Center`。
  - `HorizontalAlignment`: 水平對齊方式，如 `Left`、`Right`、`Center`。

### `FontSize` 和 `FontWeight`
- **說明**: 控制文字的大小和粗細。例如，`FontSize="18"` 設置文字大小為 18，`FontWeight="Bold"` 設置文字為粗體。

### `TextWrapping`
- **說明**: 控制文本是否自動換行。`TextWrapping="Wrap"` 表示文本會在達到控件邊界時自動換行。

### `Content`
- **說明**: 控件顯示的內容，常用於 `Button`、`RadioButton`、`Label` 等控件。例如，`Content="確定訂購"` 設置按鈕上顯示的文字為「確定訂購」。

### `GroupName`
- **說明**: 將多個 `RadioButton` 分組，確保在同一組內只有一個選項被選中。例如，`GroupName="DiningOption"` 將「內用」和「外帶」兩個 `RadioButton` 分為一組。

## 6. 事件處理器

### `Click="OrderButton_Click"`
- **說明**: 定義當按鈕被點擊時觸發的事件處理器。在後端 C# 代碼中，您需要實現 `OrderButton_Click` 方法來處理訂單邏輯。

## 7. 佈局與樣式

### `StackPanel`
- **說明**: 一種簡單的佈局容器，用於垂直或水平排列子元素。在此例中，主要用於排列飲料菜單項目和內用/外帶選項。

### `Grid`
- **說明**: 一種靈活的佈局容器，可以通過行和列來排列子元素。在此例中，`Grid` 作為主要佈局容器，包含所有子控制項，使得界面結構更為清晰和靈活。

### `Margin` 和 `Padding`
- **Margin**: 控制控件與其外部邊界的距離，用於調整控件之間的間距。
- **Padding**: 控制控件內部內容與其邊界的距離，用於調整控件內部內容的間距。例如，`Padding="5,5,5,5"` 為 `TextBlock` 內部添加了 5 像素的填充。

## 8. 控制項功能

### 8.1. `stackpanel_DrinkMenu`
- **功能**: 用於顯示可供選擇的飲料菜單項目。通常，您會在後端代碼中動態添加 `RadioButton` 或其他選項控件到此 `StackPanel`，以供用戶選擇。

### 8.2. `OrderButton`
- **功能**: 用戶點擊此按鈕後，系統會根據選擇的飲料和用餐方式進行訂單處理，並在 `ResultTextBlock` 顯示訂單結果。

### 8.3. `ResultTextBlock`
- **功能**: 顯示用戶的訂單結果或相關信息。例如，顯示所選擇的飲料、用餐方式以及訂單總額等。

### 8.4. `GroupBox` 內的 `RadioButton`
- **功能**: 讓用戶選擇訂單的用餐方式，即「內用」或「外帶」。通過 `GroupName="DiningOption"` 確保用戶只能選擇其中一個選項。

## 9. 後端代碼（C#）的關聯

雖然這段 XAML 程式碼主要定義了 UI 的結構和外觀，但實際的功能實現需要在後端的 C# 代碼中完成。例如：

- **初始化飲料菜單**: 在 `MainWindow` 的構造函數中，您可能會動態添加飲料選項到 `stackpanel_DrinkMenu`。
  
  ```csharp
  public MainWindow()
  {
      InitializeComponent();
      PopulateDrinkMenu();
  }

  private void PopulateDrinkMenu()
  {
      // 示例：添加幾個飲料選項
      string[] drinks = { "咖啡", "茶", "果汁", "汽水" };
      foreach (var drink in drinks)
      {
          RadioButton rb = new RadioButton
          {
              Content = drink,
              FontSize = 16,
              Margin = new Thickness(5)
          };
          stackpanel_DrinkMenu.Children.Add(rb);
      }
  }
  ```

- **處理訂單邏輯**: 在 `OrderButton_Click` 方法中，您需要收集用戶的選擇並顯示結果。

  ```csharp
  private void OrderButton_Click(object sender, RoutedEventArgs e)
  {
      // 獲取選擇的飲料
      string selectedDrink = "";
      foreach (RadioButton rb in stackpanel_DrinkMenu.Children.OfType<RadioButton>())
      {
          if (rb.IsChecked == true)
          {
              selectedDrink = rb.Content.ToString();
              break;
          }
      }

      // 獲取用餐方式
      string diningOption = DineInRadioButton.IsChecked == true ? "內用" : "外帶";

      // 顯示結果
      if (!string.IsNullOrEmpty(selectedDrink))
      {
          ResultTextBlock.Text = $"您選擇的飲料是：{selectedDrink}\n用餐方式：{diningOption}";
      }
      else
      {
          ResultTextBlock.Text = "請選擇一種飲料。";
      }
  }
  ```

## 10. 總結

這段 XAML 程式碼定義了一個簡單的飲料點餐系統界面，主要包含以下功能：

- **飲料選擇**: 通過 `StackPanel` 動態顯示飲料選項，使用戶可以選擇自己喜歡的飲料。
- **用餐方式選擇**: 通過 `GroupBox` 和 `RadioButton` 讓用戶選擇「內用」或「外帶」。
- **訂單確認**: 通過 `Button` 觸發訂單處理，並在 `TextBlock` 中顯示訂單結果。

## 1. 基本結構

### `<Window>`
- **說明**: WPF 應用程式的主要視窗容器。所有其他 UI 元素都嵌套在此元素內。
- **屬性**:
  - `x:Class`: 指定這個視窗對應的後端 C# 類別。
  - `xmlns`: 定義命名空間，用於引用不同的 XML 命名空間。
  - `Title`: 視窗的標題。
  - `Height` 和 `Width`: 視窗的高度和寬度。

### `DockPanel`
- **說明**: 一種佈局容器，允許其子元素依次停靠在上、下、左、右或填滿剩餘空間。
- **屬性**:
  - `LastChildFill`: 控制最後一個子元素是否填滿剩餘空間。設為 `False` 表示最後一個子元素不會自動填滿。

## 2. 命名空間（Namespaces）

- `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`: WPF 的主要命名空間，包含大部分 UI 控件。
- `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`: XAML 的基本命名空間，包含 XAML 的基本功能如 `x:Name`、`x:Class` 等。
- `xmlns:d` 和 `xmlns:mc`: 用於設計時支援（Design-Time Support）的命名空間。
- `xmlns:local="clr-namespace:_2024_WpfApp4"`: 定義本地程式集中定義的類別和控制項的命名空間。
- `xmlns:xctk="http://schemas.xceed.com/wpf/xaml/toolkit"`: 引用第三方的 WPF 工具包（Extended WPF Toolkit），提供更多的控制項，如 `ColorPicker`。

## 3. 菜單（Menu）

### `<Menu>`
- **說明**: 提供應用程式的選單列，通常放置在視窗的頂部。
- **屬性**:
  - `Height`: 菜單的高度。
  - `DockPanel.Dock`: 指定此元素在 `DockPanel` 中的停靠位置，此處設為 `Top`。

### `<MenuItem>`
- **說明**: 菜單中的每個選項。
- **屬性**:
  - `Header`: 顯示在菜單中的文字。
  - 內部還包含其他 `<MenuItem>`，表示子選項，如 "開新檔案"、"開啟舊檔" 等。

## 4. 工具列（ToolBarTray 和 ToolBar）

### `<ToolBarTray>`
- **說明**: 容納一組 `ToolBar` 控件的容器，允許多個工具列的佈局。
- **屬性**:
  - `Height`: 工具列托盤的高度。
  - `DockPanel.Dock`: 設置停靠位置，此處為 `Top`。

### `<ToolBar>`
- **說明**: 包含工具按鈕、控制項等的工具列。
- **屬性**:
  - `Height` 和 `Width`: 工具列的尺寸。
  - `Background`: 背景顏色。
  - `Margin`: 控制工具列的外邊距。

#### 第一個 `<ToolBar>` 內容：
- **Label**: 用於顯示文字，如 "筆刷色彩" 和 "填滿色彩"。
- **`<xctk:ColorPicker>`**: 來自 Extended WPF Toolkit 的色彩選擇器，允許用戶選擇顏色。
  - `x:Name`: 控件的名稱，用於在後端代碼中引用。
  - `Width`: 控件的寬度。
  - `DisplayColorAndName`: 是否同時顯示顏色和名稱。

- **`<Slider>`**: 滑動條，用於調整筆刷的粗細。
  - `x:Name`: 控件名稱。
  - `Minimum` 和 `Maximum`: 滑動條的最小和最大值。
  - `Value`: 當前值。
  - `TickFrequency`: 標記的頻率。
  - `IsSnapToTickEnabled`: 是否自動對齊到標記值。
  - `ValueChanged`: 值改變時觸發的事件處理器。

#### 第二個 `<ToolBar>` 內容：
- **`<RadioButton>`**: 單選按鈕，用於選擇繪圖的形狀（如線條、矩形、椭圓、多邊線）。
  - `Width` 和 `Height`: 按鈕尺寸。
  - `Click`: 點擊時觸發的事件處理器。
  - `Tag`: 用於標識選擇的形狀類型。
  - 內部包含 `<Image>`，顯示對應形狀的圖示。

- **`<Separator>`**: 分隔線，用於在工具列中分隔不同的控制項。

## 5. 畫布（Canvas）

### `<Canvas>`
- **說明**: 一個自由佈局的容器，允許在其中絕對定位子元素，常用於繪圖應用。
- **屬性**:
  - `x:Name`: 控件名稱，用於在後端代碼中引用。
  - `DockPanel.Dock`: 停靠位置，此處為 `Top`。
  - `Height`: 畫布的高度。
  - `Background`: 背景顏色。
  
- **事件**:
  - `MouseEnter`: 當滑鼠進入畫布時觸發。
  - `MouseLeftButtonDown`: 滑鼠左鍵按下時觸發。
  - `MouseMove`: 滑鼠移動時觸發。
  - `MouseLeftButtonUp`: 滑鼠左鍵鬆開時觸發。

## 6. 狀態列（StatusBar）

### `<StatusBar>`
- **說明**: 顯示應用程式的狀態資訊，通常放置在視窗底部。
- **屬性**:
  - `Height`: 狀態列的高度。
  - `DockPanel.Dock`: 停靠位置，此處為 `Bottom`。
  - `Background`: 背景顏色。

### `<StatusBarItem>`
- **說明**: 狀態列中的每個項目。
- **內容**:
  - `<Label>`: 顯示文字資訊，如 "Ready" 和點擊時的座標資訊。
    - `x:Name`: 控件名稱。
    - `Content`: 顯示的內容。
    - `Width`: 控件寬度。
    - 其他屬性如 `VerticalContentAlignment`、`HorizontalContentAlignment`、`FontWeight`、`FontSize` 用於控制文本的對齊和樣式。

## 7. 事件處理器

### `strokeThicknessSlider_ValueChanged`
- **說明**: 當滑動條的值改變時觸發，用於更新筆刷的粗細。

### `ShapeButton_Click`
- **說明**: 當形狀選擇按鈕被點擊時觸發，用於選擇當前繪圖的形狀（線條、矩形等）。

### `myCanvas_MouseEnter`, `myCanvas_MouseLeftButtonDown`, `myCanvas_MouseMove`, `myCanvas_MouseLeftButtonUp`
- **說明**: 與畫布互動相關的事件處理器，用於實現繪圖功能，如開始繪製、移動繪製、完成繪製等。

## 8. 控制項屬性詳解

### `x:Name`
- **說明**: 為 XAML 控件指定名稱，使其在後端代碼（如 C#）中可被引用和操作。

### `Width` 和 `Height`
- **說明**: 控制項的寬度和高度。

### `Background`
- **說明**: 控制項的背景顏色，可以使用十六進位色碼或系統顏色名稱。

### `FontSize` 和 `FontWeight`
- **說明**: 控制文字的大小和粗細。

### `Margin`
- **說明**: 控制項的外邊距，用於調整控件之間的間距。

### `Content`
- **說明**: 控制項顯示的內容，常用於 `Label`、`Button` 等控件。

## 9. 第三方控件

### `<xctk:ColorPicker>`
- **說明**: 來自 Extended WPF Toolkit 的色彩選擇器控件，提供用戶友好的顏色選擇界面。
- **屬性**:
  - `DisplayColorAndName`: 控制是否同時顯示顏色和名稱。
  - `x:Name`: 控件名稱，用於在後端代碼中引用選擇的顏色。

## 10. 圖片資源

### `<Image>`
- **說明**: 顯示圖片的控件。
- **屬性**:
  - `Height` 和 `Width`: 圖片的尺寸。
  - `Source`: 圖片的來源路徑，這裡指向應用程式中的資源，如 `/line.png`、`/rectangle.png` 等。

## 11. 樣式與佈局

### `DockPanel.Dock`
- **說明**: 定義子元素在 `DockPanel` 中的停靠位置，如 `Top`、`Bottom`、`Left`、`Right` 等。

### `LastChildFill`
- **說明**: 控制 `DockPanel` 中最後一個子元素是否填滿剩餘空間。設為 `False` 表示最後一個子元素不會自動填滿，這在本例中是為了讓 `Canvas` 和 `StatusBar` 保持固定尺寸。

## 總結

這段 XAML 程式碼定義了一個具有菜單列、工具列、繪圖畫布和狀態列的基本 WPF 繪圖應用程式界面。主要功能包括：
- 創建和管理檔案（開新檔案、開啟舊檔、儲存、另存新檔、結束）。
- 選擇筆刷色彩和填滿色彩。
- 調整筆刷粗細。
- 選擇繪圖形狀（線條、矩形、椭圓、多邊線）。
- 在畫布上進行繪圖操作，並在狀態列顯示當前狀態和滑鼠座標。
