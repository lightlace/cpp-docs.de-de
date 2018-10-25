---
title: Fensterklassen-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e151ba4fc2adbe6dab2397d68658b0cb1eb5ef1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059076"
---
# <a name="window-class-macros"></a>Fensterklassen-Makros

Diese Makros definieren Hilfsprogramme für Fenster-Klasse.

|||
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|Können Sie den Namen der eine neue Windows-Klasse angeben.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Ermöglicht Ihnen, geben Sie den Namen, der eine neue Windows-Klasse und der einschließenden Klasse, dessen Fensterprozedur die neue Klasse verwendet wird.|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Können Sie den Namen der eine vorhandene Fensterklasse angeben, auf dem eine neue Windows-Klasse basieren soll.|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Können Sie die Parameter einer Klasse angeben.|

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="declare_wnd_class"></a>  DECLARE_WND_CLASS

Können Sie den Namen der eine neue Windows-Klasse angeben. Platzieren Sie dieses Makro in der Steuerelementklasse eines ATL-ActiveX-Steuerelements.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>Parameter

*WndClassName*<br/>
[in] Der Name der neuen Window-Klasse. Wenn der Wert NULL ist, generiert ATL einen Klassennamen der Fenster.

### <a name="remarks"></a>Hinweise

Wenn Sie die Option /permissive-compiler verwenden, klicken Sie dann verursachen DECLARE_WND_CLASS einen Compilerfehler. Verwenden Sie stattdessen DECLARE_WND_CLASS2.

DECLARE_WND_CLASS können Sie den Namen der eine neue Windows-Klasse angeben, deren Informationen werden vom verwaltet [CWndClassInfo](cwndclassinfo-class.md). DECLARE_WND_CLASS definiert die neue Windows-Klasse, durch die folgenden statischen Funktion zu implementieren:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS gibt an, die folgenden Stile für das neue Fenster:

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS gibt auch die Hintergrundfarbe des Standard-Fensters. Verwenden der [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) Makro, geben Sie Ihre eigenen Formatvorlagen und Hintergrundfarbe.

[CWindowImpl](cwindowimpl-class.md) verwendet die DECLARE_WND_CLASS-Makro, um ein Fenster, die basierend auf einem neuen Fensterklasse zu erstellen. Um dieses Verhalten überschreiben, verwenden die [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) -Makro, oder geben Sie eine eigene Implementierung der [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) Funktion.

Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).

##  <a name="declare_wnd_class2"></a>  DECLARE_WND_CLASS2

(Visual Studio 2017) Ähnlich wie DECLARE_WND_CLASS, aber mit einem zusätzlichen Parameter, der einen abhängiger Namenfehler verhindert, bei der Kompilierung mit der PERMISSIVE.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>Parameter

*WndClassName*<br/>
[in] Der Name der neuen Window-Klasse. Wenn der Wert NULL ist, generiert ATL einen Klassennamen der Fenster.

*EnclosingClass*<br/>
[in] Der Name der Fensterklasse, die die neue Windows-Klasse umschließt. Darf nicht NULL sein.

### <a name="remarks"></a>Hinweise

Wenn Sie die PERMISSIVE verwenden, wird DECLARE_WND_CLASS einem Kompilierungsfehler führen, da sie einen abhängigen Namen enthält. DECLARE_WND_CLASS2 müssen Sie die Klasse, dass dieses Makro wird verwendet, und nicht, dass den Fehler unter den /permissive-flag bewirkt explizit zu benennen.
Andernfalls ist dieses Makro mit [DECLARE_WND_CLASS](#declare_wnd_class).

##  <a name="declare_wnd_superclass"></a>  DECLARE_WND_SUPERCLASS

Können Sie die Parameter einer Klasse angeben. Platzieren Sie dieses Makro in der Steuerelementklasse eines ATL-ActiveX-Steuerelements.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>Parameter

*WndClassName*<br/>
[in] Der Name des Fensters Klasse diese Informationen werden *OrigWndClassName*. Wenn der Wert NULL ist, generiert ATL einen Klassennamen der Fenster.

*OrigWndClassName*<br/>
[in] Der Name der eine vorhandene Fensterklasse.

### <a name="remarks"></a>Hinweise

Dieses Makro können Sie den Namen des eine Fensterklasse, die übergeordnete Klasse eine vorhandene Fensterklasse angeben. [CWndClassInfo](cwndclassinfo-class.md) verwaltet die Informationen der übergeordneten Klasse.

DECLARE_WND_SUPERCLASS implementiert die folgende statische Funktion:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

In der Standardeinstellung [CWindowImpl](cwindowimpl-class.md) verwendet die [DECLARE_WND_CLASS](#declare_wnd_class) Makro beim Erstellen eines Fensters auf der Grundlage von einer neue Windows-Klasse. Durch Angabe der DECLARE_WND_SUPERCLASS-Makro in einem `CWindowImpl`-abgeleitete Klasse sein, die Fensterklasse basiert auf einer vorhandenen Klasse jedoch der Fensterprozedur verwenden. Dieses Verfahren wird die Erstellung einer übergeordneten Klasse bezeichnet.

Sie können neben dem Verwenden der Makros DECLARE_WND_CLASS und DECLARE_WND_SUPERCLASS, überschreiben die [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) Funktion durch eine eigene Implementierung.

Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).

##  <a name="declare_wnd_class_ex"></a>  DECLARE_WND_CLASS_EX

Können Sie den Namen der eine vorhandene Fensterklasse angeben, auf dem eine neue Windows-Klasse basieren soll. Platzieren Sie dieses Makro in der Steuerelementklasse eines ATL-ActiveX-Steuerelements.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>Parameter

*WndClassName*<br/>
[in] Der Name der neuen Window-Klasse. Wenn der Wert NULL ist, generiert ATL einen Klassennamen der Fenster.

*Stil*<br/>
[in] Der Stil des Fensters.

*Hintergrund*<br/>
[in] Die Hintergrundfarbe des Fensters.

### <a name="remarks"></a>Hinweise

Dieses Makro können Sie die Klasse-Parameter, der eine neue Windows-Klasse angeben, deren Informationen werden vom verwaltet [CWndClassInfo](cwndclassinfo-class.md). DECLARE_WND_CLASS_EX definiert die neue Windows-Klasse, durch die folgenden statischen Funktion zu implementieren:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Wenn Sie die Standardstile und Hintergrundfarbe verwenden möchten, verwenden Sie die [DECLARE_WND_CLASS](#declare_wnd_class) Makro. Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).

## <a name="see-also"></a>Siehe auch

[Makros](atl-macros.md)

