---
title: "Windows Support Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.windows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Fenster"
  - "windows [C++], ATL"
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Windows Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Klassen bieten Unterstützung für Fenster:  
  
-   [\_U\_MENUorID](../atl/reference/u-menuorid-class.md) stellt Wrapper für **CreateWindow** und **CreateWindowEx** bereit.  
  
-   [CWindow](../atl/reference/cwindow-class.md) enthält Methoden zum Bearbeiten eines Fensters.  `CWindow` ist die Basisklasse für `CWindowImpl`, `CDialogImpl` und `CContainedWindow`.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) implementiert ein Fenster auf einer neuen Fensterklasse.  Ermöglicht es auch zur Unterklasse oder der übergeordneten Klasse das Fenster.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) implementiert ein Dialogfeld.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) implementiert ein modales Dialogfeld \(oder nicht modale\) dieses Hosts ActiveX\-Steuerelemente.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) implementiert ein modales Dialogfeld \(oder nicht modale\) mit grundlegenden Funktionalität.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) bearbeitet ein Fenster, das ein ActiveX\-Steuerelement hostet.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) stellt Methoden zum Bearbeiten eines Fensters bereit, das ein ActiveX\-Steuerelement hostet und auch Unterstützung für das Hosten von lizenzierten ActiveX\-Steuerelemente verfügt.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) implementiert ein Fenster, das innerhalb eines anderen Objekts enthalten ist.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) verwaltet die Informationen einer neuen Fensterklasse.  
  
-   [CDynamicChain](../atl/reference/cdynamicchain-class.md) Stützdynamische Verketten von Meldungszuordnungen.  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) können Objekte, um seine Meldungszuordnungen anderen Objekten verfügbar zu machen.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) stellt eine einfache Methode der Normung der Merkmale eines ATL\-Fensterobjekts.  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) stellt Standardwerte für Fensterstile und die erweiterten Stile, die verwendet werden, um ein Fenster zu erstellen.  Diese Werte werden, mithilfe des logischen OR\-Operators, auf Werte hinzugefügt, die bei der Erstellung eines Fensters bereitgestellt werden.  
  
## Verwandte Elemente  
 [ATL\-Fensterklassen](../atl/atl-window-classes.md)  
  
 [ATL\-Lernprogramm](../atl/active-template-library-atl-tutorial.md)  
  
## Siehe auch  
 [Class Overview](../atl/atl-class-overview.md)   
 [Message Map Macros](../atl/reference/message-map-macros-atl.md)   
 [Window Class Macros](../atl/reference/window-class-macros.md)