---
title: Zuordnen von GDI-Ressourcen | Microsoft Docs
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
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ef6b784a04b7be29b470b92aa09bef8bda449e2
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="allocating-gdi-resources"></a>Zuordnen von GDI-Ressourcen
In diesem Artikel wird beschrieben, wie Sie die für das Drucken benötigten Objekte der Windows-GDI (Graphics Device Interface) zuweisen und ihre Zuweisung aufheben.  
  
> [!NOTE]
>  Weitere Informationen finden Sie unter den GDI + SDK-Dokumentation unter: [http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Angenommen, Sie müssen bestimmte Schriften, Stifte oder andere GDI-Objekte für das Drucken, aber nicht für die Bildschirmanzeige verwenden. Aufgrund des erforderlichen Arbeitsspeichers ist es ineffizient, diese Objekte beim Start der Anwendung zuzuordnen. Wenn die Anwendung gerade kein Dokument druckt, wird dieser Speicher möglicherweise für andere Zwecke benötigt. Es ist besser, sie bei Beginn des Druckens zuzuordnen und nach dem Druckvorgang zu löschen.  
  
 Um diese GDI-Objekte zuzuordnen, überschreiben die [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) Memberfunktion. Diese Funktion ist aus zwei Gründen gut für diesen Zweck geeignet: das Framework ruft diese Funktion einmal zu Beginn jedes Druckauftrags auf und im Gegensatz zu [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), diese Funktion hat Zugriff auf die [CDC](../mfc/reference/cdc-class.md) das Objekt, das den Druckertreiber darstellt. Sie können diese Objekte für die Verwendung während des Druckauftrags speichern, indem das Definieren von Membervariablen in Ihrer Ansichtsklasse, die auf GDI-Objekte verweisen (z. B. **CFont \***  Mitglieder usw.).  
  
 Um die GDI-Objekte verwenden Sie erstellt haben, wählen Sie diese den Drucker-Gerätekontext in der [OnPrint](../mfc/reference/cview-class.md#onprint) Memberfunktion. Wenn Sie unterschiedliche GDI-Objekte für verschiedene Seiten des Dokuments benötigen, können Sie untersuchen die `m_nCurPage` Mitglied der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) Struktur und das GDI-Objekt entsprechend wählen. Wenn Sie ein GDI-Objekt für mehrere aufeinanderfolgende Seiten benötigen, müssen Sie es bei jedem Aufrufen von `OnPrint` in den Gerätekontext wählen.  
  
 Um diese GDI-Objekte aufzuheben, überschreiben die [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) Memberfunktion. Das Framework ruft diese Funktion am Ende jedes Druckauftrags auf, wodurch Sie die Zuweisung druckspezifischer GDI-Objekte aufheben können, bevor die Anwendung zu anderen Aufgaben zurückkehrt.  
  
## <a name="see-also"></a>Siehe auch  
 [Drucken](../mfc/printing.md)   
 [Funktionsweise des Standarddrucks](../mfc/how-default-printing-is-done.md)

