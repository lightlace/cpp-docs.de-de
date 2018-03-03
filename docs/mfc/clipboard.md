---
title: Zwischenablage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 304f20f94880b0bd8cb671788c5c06b69d25d377
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard"></a>Zwischenablage
Diese Artikelreihe erläutert die Unterstützung für die Windows-Zwischenablage in MFC-Anwendungen implementieren. Die Windows-Zwischenablage wird auf zwei Arten verwendet:  
  
-   Implementieren standard bearbeiten Menübefehlen, wie Ausschneiden, kopieren und einfügen.  
  
-   Implementieren von uniform Data transfer mit Drag und drop (OLE).  
  
 Die Zwischenablage ist die Windows-Standardmethode der Übertragung von Daten zwischen einer Quelle und ein Ziel. Es kann auch in OLE-Vorgängen sehr nützlich sein. Durch die Einführung von OLE gibt es zwei Mechanismen der Zwischenablage in Windows. Der standardmäßigen Windows-Zwischenablage-API ist noch verfügbar, aber es wurde mit der OLE-Datenübertragungsmechanismus ergänzt wurden. OLE einheitliche Datenübertragung (UDT) unterstützt, Ausschneiden, kopieren und Einfügen mit der Zwischenablage und Drag & drop.  
  
 Die Zwischenablage ist ein Systemdienst, die von der gesamten Windows-Sitzung freigegeben wird, damit sie nicht über ein Handle oder der Klasse selbst verfügt. Sie verwalten die Zwischenablage über Memberfunktionen der Klasse [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Verwenden des jeweiligen zwischenablagemechanismus](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [Mithilfe der herkömmlichen Windows-Zwischenablage-API](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [Verwenden des OLE-zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)  
  
-   [Die Windows-Zwischenablage](https://msdn.microsoft.com/library/ms648709)  
  
-   [Implementieren von Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)
