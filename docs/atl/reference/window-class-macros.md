---
title: Fenster Makros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: f32926b6efd4ffb9c0541c0574a479c13dac01df
ms.lasthandoff: 02/24/2017

---
# <a name="window-class-macros"></a>Fenster-Makros
Diese Makros definieren Dienstprogramme für Fenster-Klasse.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|Ermöglicht die Angabe einer neuen Fensterklasse.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Geben Sie den Namen einer neuen Fensterklasse und der einschließenden Klasse, deren Fensterprozedur die neue Klasse verwendet ermöglicht.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Können Sie den Namen der eine vorhandene Fensterklasse angeben, auf dem eine neue Windows-Klasse basieren soll.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Können Sie die Parameter einer Klasse angeben.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
   
##  <a name="a-namedeclarewndclassa--declarewndclass"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS  
 Ermöglicht die Angabe einer neuen Fensterklasse. Setzen Sie dieses Makro in ein ATL-ActiveX-Steuerelement-Control-Klasse.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name der neuen Fensterklasse. Wenn **NULL**, ATL einen Fensterklassennamen generiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Option /permissive-compiler verwenden, verursachen DECLARE_WND_CLASS einen Compilerfehler. Verwenden Sie stattdessen DECLARE_WND_CLASS2.
 
 DECLARE_WND_CLASS können Sie den Namen einer neuen Fensterklasse angeben, deren Informationen verwaltet [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS`definiert die neue Windows-Klasse durch die folgende statische Funktion zu implementieren:  
  
 [!code-cpp[127 NVC_ATL_Windowing](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS`Gibt die folgenden Formate für das neue Fenster an:  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS`Gibt die Hintergrundfarbe für das Standardfenster auch an. Verwenden der [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) Makro, geben Sie Ihre eigenen Formatvorlagen und Hintergrundfarbe.  
  
 [CWindowImpl](cwindowimpl-class.md) verwendet die `DECLARE_WND_CLASS` Makro zum Erstellen eines Fensters basierend auf einer neuen Fensterklasse. Um dieses Verhalten zu überschreiben, verwenden die [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) -Makro, oder geben Sie eine eigene Implementierung von der [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) Funktion.  

  
 Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  

##  <a name="a-namedeclarewndclass2a--declarewndclass2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2  
 (Visual Studio 2017) Ähnlich wie DECLARE_WND_CLASS, aber mit einem zusätzlichen Parameter, der einen abhängiger Namenfehler beseitigt, bei der Kompilierung mit der /permissive-option.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name der neuen Fensterklasse. Wenn **NULL**, ATL einen Fensterklassennamen generiert. 

 `EnclosingClass`  
 [in] Der Name der Fensterklasse, die die neue Windows-Klasse enthält. Nicht **NULL**.  
  
### <a name="remarks"></a>Hinweise 
Wenn Sie die /permissive-option verwenden, wird DECLARE_WND_CLASS einen Kompilierungsfehler verursachen, da es sich um ein abhängiger Name enthält. DECLARE_WND_CLASS2 erfordert, dass Sie die Klasse, dass dieses Makro in verwendet wird und nicht dazu, der Fehler tritt unter den /permissive-flag dass explizit zu benennen.
Andernfalls ist dieses Makro mit [DECLARE_WND_CLASS](#declare_wnd_class).
   
##  <a name="a-namedeclarewndsuperclassa--declarewndsuperclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS  
 Können Sie die Parameter einer Klasse angeben. Setzen Sie dieses Makro in ein ATL-ActiveX-Steuerelement-Control-Klasse.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name des Fensters, werden Informationen zur übergeordneten Klasse `OrigWndClassName`. Wenn **NULL**, ATL einen Fensterklassennamen generiert.  
  
 `OrigWndClassName`  
 [in] Der Name der eine vorhandene Fensterklasse.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro können Sie den Namen einer Fensterklasse, die übergeordnete Klasse eine vorhandene Fensterklasse angeben. [CWndClassInfo](cwndclassinfo-class.md) verwaltet die Informationen der übergeordneten Klasse.  
  
 `DECLARE_WND_SUPERCLASS`implementiert die folgenden statischen Funktion:  
  
 [!code-cpp[127 NVC_ATL_Windowing](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 In der Standardeinstellung [CWindowImpl](cwindowimpl-class.md) verwendet die [DECLARE_WND_CLASS](#declare_wnd_class) Makro zum Erstellen eines Fensters basierend auf einer neuen Fensterklasse. Durch Angabe der `DECLARE_WND_SUPERCLASS` Makro in eine `CWindowImpl`-abgeleiteten Klasse Window-Klasse auf einer vorhandenen Klasse basiert, jedoch wird der Fensterprozedur verwendet. Diese Technik wird das Erstellen von übergeordneten Klassen bezeichnet.  
  
 Neben der Verwendung der `DECLARE_WND_CLASS` und `DECLARE_WND_SUPERCLASS` Makros, die Sie überschreiben die [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) Funktion durch eine eigene Implementierung.  

  
 Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  
  
##  <a name="a-namedeclarewndclassexa--declarewndclassex"></a><a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX  
 Können Sie den Namen der eine vorhandene Fensterklasse angeben, auf dem eine neue Windows-Klasse basieren soll. Setzen Sie dieses Makro in ein ATL-ActiveX-Steuerelement-Control-Klasse.  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name der neuen Fensterklasse. Wenn **NULL**, ATL einen Fensterklassennamen generiert.  
  
 `style`  
 [in] Der Stil des Fensters.  
  
 *Hintergrund*  
 [in] Die Hintergrundfarbe des Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro können Sie die Klasse-Parameter, der eine neue Windows-Klasse angeben, deren Informationen verwaltet [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS_EX`definiert die neue Windows-Klasse durch die folgende statische Funktion zu implementieren:  
  
 [!code-cpp[127 NVC_ATL_Windowing](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Wenn Sie die Standardstile und Hintergrundfarbe verwenden möchten, verwenden Sie die [DECLARE_WND_CLASS](#declare_wnd_class) Makro. Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](atl-macros.md)










