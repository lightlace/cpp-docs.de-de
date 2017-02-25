---
title: "Introduction to ATL Window Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "window classes"
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Introduction to ATL Window Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden ATL\-Klassen wurden entwickelt, um Fenster zu implementieren und zu bearbeiten:  
  
-   [CWindow](../atl/reference/cwindow-class.md) ermöglicht es Ihnen, ein Fensterhandle zum `CWindow`\-Objekt anzufügen.  Rufen Sie dann `CWindow`\-Methoden auf, um das Fenster zu bearbeiten.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) ermöglicht es Ihnen, ein neues Fenster und Meldungen verarbeiten mit einer Meldungszuordnung zu implementieren.  Sie können ein Fenster auf Grundlage einer neue Windows\-Klasse, übergeordnete Klasse erstellen eine vorhandene Klasse, oder ordnen Sie ein vorhandenes Fenster unter.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) ermöglicht es Ihnen, modalen oder eines nicht modalen Dialogfelds und des Prozesses Meldungen mit einer Meldungszuordnung zu implementieren.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) ist eine vordefinierte Klasse, die ein Fenster implementiert wird, die Meldungszuordnung in einer anderen Klasse enthalten ist.  Verwenden `CContainedWindowT` ermöglicht es Ihnen, um die Meldung zu zentralisieren, die in einer Klasse verarbeitet.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ermöglicht es Ihnen, um ein Dialogfeld zu implementieren \(modal oder nicht modale\) dieses Hosts ActiveX\-Steuerelemente.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) ermöglicht es Ihnen, ein modales Dialogfeld mit grundlegenden Funktionalität zu implementieren.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) ermöglicht es Ihnen, ein Fenster implementieren, das ein ActiveX\-Steuerelement hostet.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) ermöglicht es Ihnen, ein Fenster implementieren, das ein lizenziertes ActiveX\-Steuerelement hostet.  
  
 Zusätzlich zu den bestimmten Fensterklassen ATL stellt mehrere Klassen, die entwickelt wurden, um die Implementierung von einem ATL\-Fensterobjekt zu vereinfachen.  Dies sind:  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) verwaltet die Informationen einer neuen Fensterklasse.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) und [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) bieten eine einfache Methode der Normung der Merkmale eines ATL\-Fensterobjekts.  
  
## Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)