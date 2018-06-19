---
title: Fenster Klasse Makros | Microsoft Docs
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
ms.openlocfilehash: f0490eedb412e43f2ae99c4034648880be5f32a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364231"
---
# <a name="window-class-macros"></a>Makros für Fenster-Klasse
Diese Makros definieren Hilfsprogramme für Fenster-Klasse.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|Können Sie den Namen einer neuen Fensterklasse angeben.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Bietet die Möglichkeit, geben Sie den Namen einer neuen Fensterklasse und der einschließenden Klasse, deren Fensterprozedur auf die neue Klasse verwendet wird.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Können Sie den Namen der eine vorhandene Fensterklasse überordnen angeben, auf dem eine neue Fensterklasse basieren soll.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Können Sie die Parameter einer Klasse angeben.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
   
##  <a name="declare_wnd_class"></a>  DECLARE_WND_CLASS  
 Können Sie den Namen einer neuen Fensterklasse angeben. Platzieren Sie dieses Makro in eine ATL-ActiveX-Steuerelement-Control-Klasse.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name der neuen Fensterklasse. Wenn **NULL**, ATL generiert einen Fensterklassennamen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Option /permissive-compiler verwenden, verursachen DECLARE_WND_CLASS ein Compilerfehler ausgelöst. Verwenden Sie stattdessen DECLARE_WND_CLASS2.
 
 DECLARE_WND_CLASS können Sie den Namen einer neuen Fensterklasse angeben, deren Informationen werden durch verwaltet [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS` definiert die neue Windows-Klasse implementiert die folgenden statische Funktion:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS` Gibt die folgenden Stile für das neue Fenster an:  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS` Gibt die Hintergrundfarbe der Standardfenster auch an. Verwenden der [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) Makro eigener Formatvorlagen und Hintergrundfarbe.  
  
 [CWindowImpl](cwindowimpl-class.md) verwendet die `DECLARE_WND_CLASS` Makro beim Erstellen eines Fensters basierend auf einem neuen Fensterklasse. Um dieses Verhalten zu überschreiben, verwenden die [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) -Makro, oder eine eigene Implementierung bereitstellen, die [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) Funktion.  

  
 Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  

##  <a name="declare_wnd_class2"></a>  DECLARE_WND_CLASS2  
 (Visual Studio 2017) Ähnlich wie DECLARE_WND_CLASS, aber mit einem zusätzlichen Parameter, der einen abhängiger Namenfehler vermeidet beim Kompilieren mit der /permissive-option.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name der neuen Fensterklasse. Wenn **NULL**, ATL generiert einen Fensterklassennamen. 

 `EnclosingClass`  
 [in] Der Name der Fensterklasse, die die neue Windows-Klasse enthält. Nicht mit **NULL**.  
  
### <a name="remarks"></a>Hinweise 
Bei Verwendung der /permissive-option wird DECLARE_WND_CLASS einem Kompilierungsfehler führen, da sie einen abhängigen Namen enthält. DECLARE_WND_CLASS2 erfordert, dass Sie die Klasse, dass dieses Makro wird verwendet, und nicht dazu, der Fehler tritt unter den /permissive-flag dass führt explizit zu benennen.
Dieses Makro ist andernfalls mit [DECLARE_WND_CLASS](#declare_wnd_class).
   
##  <a name="declare_wnd_superclass"></a>  DECLARE_WND_SUPERCLASS  
 Können Sie die Parameter einer Klasse angeben. Platzieren Sie dieses Makro in eine ATL-ActiveX-Steuerelement-Control-Klasse.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name des Fensters Klasse diese Informationen werden `OrigWndClassName`. Wenn **NULL**, ATL generiert einen Fensterklassennamen.  
  
 `OrigWndClassName`  
 [in] Der Name einer vorhandenen Fenster-Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro können Sie den Namen des eine Fensterklasse, die übergeordnete Klasse eine vorhandene Fensterklasse überordnen angeben. [CWndClassInfo](cwndclassinfo-class.md) verwaltet die Informationen der übergeordneten Klasse.  
  
 `DECLARE_WND_SUPERCLASS` implementiert die folgenden statische Funktion:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Standardmäßig [CWindowImpl](cwindowimpl-class.md) verwendet die [DECLARE_WND_CLASS](#declare_wnd_class) Makro beim Erstellen eines Fensters basierend auf einem neuen Fensterklasse. Durch Angabe der `DECLARE_WND_SUPERCLASS` Makro in eine `CWindowImpl`-abgeleitete Klasse, die Fensterklasse basieren auf einer vorhandenen Klasse jedoch die Fensterprozedur verwendet. Diese Technik wird das Erstellen von übergeordneten Klassen bezeichnet.  
  
 Neben der Verwendung der `DECLARE_WND_CLASS` und `DECLARE_WND_SUPERCLASS` Makros, die Sie überschreiben die [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) -Funktion mit Ihrer eigenen Implementierung.  

  
 Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  
  
##  <a name="declare_wnd_class_ex"></a>  DECLARE_WND_CLASS_EX  
 Können Sie den Namen der eine vorhandene Fensterklasse überordnen angeben, auf dem eine neue Fensterklasse basieren soll. Platzieren Sie dieses Makro in eine ATL-ActiveX-Steuerelement-Control-Klasse.  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>Parameter  
 `WndClassName`  
 [in] Der Name der neuen Fensterklasse. Wenn **NULL**, ATL generiert einen Fensterklassennamen.  
  
 `style`  
 [in] Der Stil des Fensters.  
  
 *Hintergrund*  
 [in] Die Hintergrundfarbe des Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro können Sie die Klasse-Parameter, der eine neue Windows-Klasse angeben, deren Informationen werden durch verwaltet [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS_EX` definiert die neue Windows-Klasse implementiert die folgenden statische Funktion:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Wenn Sie die Standardstile und Hintergrundfarbe verwenden möchten, verwenden Sie die [DECLARE_WND_CLASS](#declare_wnd_class) Makro. Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](atl-macros.md)









