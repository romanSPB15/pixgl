# PixGL – простой 2D-графический движок на Go

**PixGL** (Pixel Graphics Library) – это лёгкий 2D-растеризатор для программного рисования примитивов. Он не требует OpenGL, Vulkan или других внешних графических API. Всё рисование происходит на CPU и сохраняется в `image.NRGBA`.

Движок идеально подходит для:

- изучения алгоритмов растеризации (линии, круги, заливка, z-буфер);
- создания музыкальных визуализаторов, демосцен, интро;
- быстрого прототипирования 2D-графики без зависимостей от GUI-фреймворков.

## Особенности

- ✅ **Чистый Go** – никакого CGO.
- ✅ **Примитивы**: залитые квадрат и круг, линия (Брезенхем), текст (встроенный шрифт), эллипс (контур).
- ✅ **Производительность** – прямая работа с пиксельным буфером.

## Установка

```bash
go get github.com/yourusername/pixgl
```

## Пример кода

```go
package main

import (
	"image/color"
	"log"

	"github.com/yourusername/pixgl"
)

func main() {
	canvas := pixgl.NewCanvas(800, 600)

	canvas.Add(pixgl.Fill(color.RGBA{30, 30, 30, 255}))           // серый фон
	canvas.Add(pixgl.FillSquare(100, 100, 300, 300, color.White)) // белый квадрат
	canvas.Add(pixgl.FillCircle(400, 300, 80, color.RGBA{255, 0, 0, 255}))
	canvas.Add(pixgl.DrawLine(50, 50, 750, 550, color.RGBA{0, 255, 0, 255}))
	canvas.Add(pixgl.Text(color.White, "Hello, PixGL!", 20, 50))

	canvas.Draw()

	if err := canvas.Save("output.png"); err != nil {
		log.Fatal(err)
	}
}

```
