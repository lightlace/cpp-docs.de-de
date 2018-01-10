---
title: "Einführung in ATL-Fensterklassen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 636fe8aa87b6880f5cda77fb46fc481d99d78a81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-atl-window-classes"></a>Einführung in ATL-Fensterklassen
Die folgenden ATL-Klassen dienen Windows zu implementieren:  
  
-   [CWindow](../atl/reference/cwindow-class.md) bietet die Möglichkeit, ein Fensterhandle zum Anfügen der `CWindow` Objekt. Rufen Sie dann `CWindow` Methoden zum Ändern des Fensters.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) können Sie ein neues Fenster zu implementieren und Verarbeiten von Nachrichten mit einer meldungszuordnung. Sie erstellen ein Fenster basierend auf einer neuen Windows-Klasse, übergeordnete Klasse einer vorhandenen Klasse oder Unterklasse ein vorhandenes Fenster.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) ermöglicht es Ihnen, eine modale oder ein nicht modales Dialogfeld Feld und Verarbeiten von Nachrichten mit einer meldungszuordnung zu implementieren.  
  
-   [CContainedWindow](../atl/reference/ccontainedwindowt-class.md) eine vorgefertigte-Klasse, die ein Fenster, dessen meldungszuordnung enthalten ist, in einer anderen Klasse implementiert, ist. Mithilfe von `CContainedWindowT` ermöglicht es Ihnen, die Verarbeitung von Nachrichten in einer Klasse zu zentralisieren.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) können Sie ein Dialogfeld (gebunden oder ungebunden) implementieren, die ActiveX-Steuerelemente hostet.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) können Sie ein modales Dialogfeld mit der grundlegenden Funktionalität zu implementieren.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) können Sie ein Fenster zu implementieren, die ein ActiveX-Steuerelement hostet.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) können Sie ein Fenster zu implementieren, die ein lizenziertes ActiveX-Steuerelement hostet.  
  
 Zusätzlich zu den spezifischen Fensterklassen stellt ATL mehrere Klassen, die entwickelt, um die Implementierung eines ATL-Fenster-Objekts zu vereinfachen. Dies sind:  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) verwaltet die Informationen in eine neue Windows-Klasse.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) und [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) bieten eine einfache Möglichkeit standardisieren die Merkmale eines ATL-Fenster-Objekts.  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)

