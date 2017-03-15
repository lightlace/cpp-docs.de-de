---
title: "Using a Window | Microsoft Docs"
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
  - "ATL, Fenster"
  - "CWindow class, about CWindow class"
  - "windows [C++], ATL"
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Using a Window
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\- Klasse [CWindow](../atl/reference/cwindow-class.md) ermöglicht es Ihnen, ein Fenster zu verwenden.  Nachdem Sie ein Fenster zu einem `CWindow`\-Objekt anfügen, können Sie `CWindow`\-Methoden dann aufrufen, um das Fenster zu bearbeiten.  `CWindow` enthält auch einen `HWND`\-Operator, um ein `CWindow`\-Objekt zu `HWND` zu konvertieren.  So können Sie ein `CWindow`\-Objekt an eine Funktion übergeben, die ein Handle für ein Fenster erforderlich.  Sie können `CWindow`\-Methodenaufrufe und Win32\-Funktionsaufrufe leicht kombinieren, ohne temporären Objekte zu erstellen.  
  
 Da `CWindow` Datenmember nur zwei \(ein Fensterhandle und die Standarddimensionen\) verfügt, wird es einen Mehraufwand nicht im Code auf.  Außerdem binden viele der `CWindow`\-Methoden einfach entsprechende Win32\-API\-Funktionen ein.  Indem `CWindow` verwendet, wird der `HWND`\-Member automatisch an die Win32\-Funktion übergeben.  
  
 Zusätzlich zu `CWindow` direkt verwenden, können Sie von ihm auch ableiten, um Daten oder Code der Klasse.  ATL selbst abgeleitet drei Klassen von `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md) und [CContainedWindowT](../atl/using-contained-windows.md).  
  
## Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)