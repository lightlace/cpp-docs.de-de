---
title: Implementieren ein Fenster mit CWindowImpl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CWindowImpl
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80aca6af847a33fd7217d0ad710c928f6d2ca32e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Implementieren ein Fenster mit CWindowImpl
Um ein Fenster zu implementieren, leiten Sie eine Klasse von `CWindowImpl`. Deklarieren Sie in der abgeleiteten Klasse eine meldungszuordnung und die Meldungshandlerfunktionen aus. Sie können nun Ihre Klasse auf drei verschiedene Arten verwenden:  
  
-   [Erstellen eines Fensters basierend auf einer neuen Windows-Klasse](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [Übergeordnete Klasse einer vorhandenen Windows-Klasse](#_atl_superclassing_an_existing_windows_class)  
  
-   [Ein vorhandenes Fenster-Unterklasse](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a>Erstellen eines Fensters basierend auf einer neuen Windows-Klasse  
 `CWindowImpl`enthält die [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) Makro zum Deklarieren von Klasseninformationen für Windows. Dieses Makro implementiert die `GetWndClassInfo` -Funktion, die verwendet [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) die Informationen des neuen Windows-Klasse definieren. Wenn `CWindowImpl::Create` aufgerufen wird, wird dieses Windows-Klasse registriert und ein neues Fenster erstellt wird.  
  
> [!NOTE]
>  `CWindowImpl`übergibt **NULL** auf die `DECLARE_WND_CLASS` -Makro, d. h. ATL generiert einen Windows-Klassennamen. Eine Zeichenfolge übergeben, um einen selbst gewählten Namen anzugeben, `DECLARE_WND_CLASS` in Ihrer `CWindowImpl`-Klasse.  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel für eine Klasse, die ein Fenster basierend auf einer neuen Windows-Klasse implementiert:  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]  
  
 Um ein Fenster zu erstellen, erstellen Sie eine Instanz des `CMyWindow` und rufen Sie anschließend die **erstellen** Methode.  
  
> [!NOTE]
>  Um die Standard-Windows-Klasseninformationen überschreiben möchten, implementieren die `GetWndClassInfo` Methode in der abgeleiteten Klasse durch Festlegen der `CWndClassInfo` Mitglieder auf die entsprechenden Werte.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a>Erstellen von übergeordneten Klassen einer vorhandenen Windows-Klasse  
 Die [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) Makro können Sie beim Erstellen eines Fensters, das einer vorhandenen Windows Klasse. Geben Sie dieses Makro in Ihrem `CWindowImpl`-Klasse. Wie alle anderen ATL-Fenster werden Nachrichten von einer meldungszuordnung behandelt.  
  
 Bei Verwendung von `DECLARE_WND_SUPERCLASS`, eine neue Windows-Klasse registriert wird. Diese neue Klasse wird die vorhandene Klasse, die Sie angeben, ersetzt jedoch die Fensterprozedur mit identisch sein `CWindowImpl::WindowProc` (oder mit der Funktion, die diese Methode überschreibt).  
  
## <a name="example"></a>Beispiel  
 Folgende ist ein Beispiel für eine Klasse, eine der standard bearbeiten Klasse:  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]  
  
 Um das Bearbeitungsfenster zu erstellen, erstellen Sie eine Instanz von `CMyEdit` und rufen Sie anschließend die **erstellen** Methode.  
  
##  <a name="_atl_subclassing_an_existing_window"></a>Erstellen von Unterklassen für ein vorhandenes Fenster  
 Um ein vorhandenes Fenster-Unterklasse, leiten Sie eine Klasse von `CWindowImpl` und eine meldungszuordnung, wie in den vorherigen zwei Fällen deklarieren. Beachten Sie jedoch, dass Sie alle Windows-Klasseninformationen nicht angeben, da Sie Unterklasse ein bereits vorhandenes Fenster werden.  
  
 Statt **erstellen**, rufen Sie `SubclassWindow` und übergeben sie das Handle zum vorhandenen Fenster Unterklasse sollen. Sobald das Fenster als Unterklasse definiert ist, wird es verwenden `CWindowImpl::WindowProc` (oder die Funktion, die diese Methode überschreibt) zur Weiterleitung von Nachrichten an die meldungszuordnung. Aufrufen, um ein untergeordnetes Fenster aus dem Objekt zu trennen, `UnsubclassWindow`. Ursprüngliche Fensterprozedur des Fensters wird dann wiederhergestellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren eines Fensters](../atl/implementing-a-window.md)

