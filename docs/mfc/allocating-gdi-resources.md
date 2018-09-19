---
title: Zuordnen von GDI-Ressourcen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f7923d36abcd0e9f6b7cb9e97072f5782178919
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208047"
---
# <a name="allocating-gdi-resources"></a>Zuordnen von GDI-Ressourcen
In diesem Artikel wird beschrieben, wie Sie die für das Drucken benötigten Objekte der Windows-GDI (Graphics Device Interface) zuweisen und ihre Zuweisung aufheben.  
  
> [!NOTE]
>  Weitere Informationen finden Sie unter der GDI +-SDK-Dokumentation unter: [ https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp ](https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Angenommen, Sie müssen bestimmte Schriften, Stifte oder andere GDI-Objekte für das Drucken, aber nicht für die Bildschirmanzeige verwenden. Aufgrund des erforderlichen Arbeitsspeichers ist es ineffizient, diese Objekte beim Start der Anwendung zuzuordnen. Wenn die Anwendung gerade kein Dokument druckt, wird dieser Speicher möglicherweise für andere Zwecke benötigt. Es ist besser, sie bei Beginn des Druckens zuzuordnen und nach dem Druckvorgang zu löschen.  
  
 Um diese GDI-Objekte zuzuordnen, überschreiben die [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) Member-Funktion. Diese Funktion eignet sich gut für diesen Zweck aus zwei Gründen: das Framework ruft diese Funktion einmal zu Beginn jedes Druckauftrags und im Gegensatz zu [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), diese Funktion hat Zugriff auf die [CDC](../mfc/reference/cdc-class.md) Objekt, das den Druckertreiber darstellt. Sie können diese Objekte für die Verwendung während des Druckauftrags speichern, indem Sie das Definieren von Membervariablen in Ihrer Ansichtsklasse, die auf GDI-Objekte verweisen (z. B. `CFont *` Elemente usw.).  
  
 Um die GDI-Objekte verwenden Sie erstellt haben, wählen Sie diese für den Drucker-Gerätekontext in der [OnPrint](../mfc/reference/cview-class.md#onprint) Member-Funktion. Wenn Sie unterschiedliche GDI-Objekte für verschiedene Seiten des Dokuments benötigen, können Sie überprüfen die `m_nCurPage` Mitglied der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) strukturieren und das GDI-Objekt entsprechend wählen. Wenn Sie ein GDI-Objekt für mehrere aufeinanderfolgende Seiten benötigen, müssen Sie es bei jedem Aufrufen von `OnPrint` in den Gerätekontext wählen.  
  
 Um diese GDI-Objekte aufzuheben, überschreiben die [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) Member-Funktion. Das Framework ruft diese Funktion am Ende jedes Druckauftrags auf, wodurch Sie die Zuweisung druckspezifischer GDI-Objekte aufheben können, bevor die Anwendung zu anderen Aufgaben zurückkehrt.  
  
## <a name="see-also"></a>Siehe auch  
 [Drucken](../mfc/printing.md)   
 [Funktionsweise des Standarddrucks](../mfc/how-default-printing-is-done.md)

