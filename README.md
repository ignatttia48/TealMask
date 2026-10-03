# 碧草面具 — SwiftUI 圖形練習

用 SwiftUI 純圖形繪製《寶可夢 朱/紫：零之秘寶 Part 1 碧之假面》傳說寶可夢**厄鬼椪**所配戴的「碧草面具」。

## 特色

這次練習刻意**不使用自訂 `Shape`（`Path`）**，整個面具只靠 SwiftUI 內建的 `Circle` 與 `Rectangle` 兩種基本圖形，透過疊加、裁切與變形組合而成：

- **`trim(from:to:)`**：把完整的圓形 / 矩形裁成弧形或半形，做出面具邊緣的輪廓與紋路線條
- **`rotationEffect`**：旋轉局部圖形，拼出面具上下左右對稱的花瓣造型
- **`scaleEffect`**（含負值 `x: -1`）：左右鏡像複製同一塊圖形，直接複製出對稱的另一半
- **`mask`**：用圓形 / 矩形疊合後的區域去裁切矩形色塊，做出面具臉部曲線、太晶紋路等細節
- **`offset`**：精準定位每一塊圖形的位置

全部圖案由約 20 多組「圓形 / 矩形 + 變形修飾器」堆疊而成，沒有用到 `Path`、`Shape` 自訂圖形或外部圖片素材。

## 專案結構

```
Class3/
├── Class3App.swift        // App 進入點
├── ContentView.swift       // 碧草面具主要繪製程式碼
└── Assets.xcassets/        // 面具配色（Color Set）
    ├── mask_top_light      // 面具頂部淺綠色
    ├── mask_top_dark       // 面具頂部深綠色（紋路）
    ├── mask_down           // 面具下半部綠色
    ├── mask_face           // 臉部膚色區塊
    └── mask_face_shadow    // 臉部陰影細節
```

## 執行方式

1. 使用 Xcode 開啟 `Class3.xcodeproj`
2. 選擇模擬器或裝置後直接 Run（⌘R），或使用 SwiftUI Preview 預覽 `ContentView`

## 環境

- Swift / SwiftUI
- Xcode
