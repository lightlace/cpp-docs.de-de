---
title: Erstellen eines CToolBarCtrl-Objekts | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CToolBarCtrl
dev_langs: C++
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eecb599d84cedd742a15c4a5572ce4c130b19669
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-ctoolbarctrl-object"></a>Erstellen eines CToolBarCtrl-Objekts
[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekte enthalten verschiedene interne Datenstrukturen – eine Liste der Schaltfläche Image Bitmaps, eine Liste der Schaltfläche Label-Zeichenfolgen und eine Liste der `TBBUTTON` Strukturen –, die ein Bild zuordnen und/oder die Zeichenfolge, die Position, Stil, State, und Befehls-ID der Schaltfläche. Jedes Element dieser Datenstrukturen wird durch einen nullbasierten Index bezeichnet. Vor der Verwendung einer `CToolBarCtrl` Objekt ist, müssen Sie diese Datenstrukturen einrichten. Eine Liste der Datenstruktur, finden Sie unter [Symbolleisten-Steuerelemente](https://msdn.microsoft.com/library/47xcww9x.aspx) im Windows SDK. Die Liste von Zeichenfolgen kann nur für Schaltfläche Bezeichnungen verwendet werden. Verbindungszeichenfolgen können über die Symbolleiste kann nicht abgerufen werden.  
  
 Verwenden einer `CToolBarCtrl` -Objekt, Sie werden in der Regel gehen Sie folgendermaßen vor:  
  
### <a name="to-use-a-ctoolbarctrl-object"></a>Verwenden ein CToolBarCtrl-Objekts  
  
1.  Erstellen der [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt.  
  
2.  Rufen Sie [erstellen](../mfc/reference/ctoolbarctrl-class.md#create) zum Erstellen von der allgemeinen Windows-Symbolleisten-Steuerelements, und fügen Sie es auf die `CToolBarCtrl` Objekt. Gegebenenfalls Bitmapbildern für Schaltflächen können Sie die Bitmaps für die Schaltfläche auf der Symbolleiste hinzufügen, durch den Aufruf [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Gegebenenfalls Zeichenfolge Bezeichnungen für Schaltflächen können Sie die Zeichenfolgen auf der Symbolleiste hinzufügen, durch den Aufruf [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) und/oder [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings). Nach dem Aufruf `AddString` und/oder `AddStrings`, rufen Sie [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) ändern, um die Zeichenfolge oder den Zeichenfolgen angezeigt werden, zu erhalten.  
  
3.  Fügen Sie der Symbolleiste durch Aufrufen von [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons).  
  
4.  Behandeln Sie ggf. QuickInfos **TTN_NEEDTEXT** Nachrichten in der Symbolleiste Besitzerfenster wie beschrieben in [Behandlung von Tool Tipp Benachrichtigungen](../mfc/handling-tool-tip-notifications.md).  
  
5.  Behandeln Sie gegebenenfalls Ihre Benutzer auf die Symbolleiste anpassen kann Anpassung von benachrichtigungsmeldungen in das besitzende Fenster wie in beschrieben [Behandeln von Anpassungsbenachrichtigungen](../mfc/handling-customization-notifications.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

