---
title: Zuordnen von GDI-Ressourcen
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 672a9a2ce103ae7f53f61ae955f77276eb1d2945
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509278"
---
# <a name="allocating-gdi-resources"></a>Zuordnen von GDI-Ressourcen

In diesem Artikel wird beschrieben, wie Sie die für das Drucken benötigten Objekte der Windows-GDI (Graphics Device Interface) zuweisen und ihre Zuweisung aufheben.

> [!NOTE]
>  Weitere Informationen finden Sie in der [GDI+-SDK-Dokumentation](/windows/win32/gdiplus/-gdiplus-gdi-start).

Angenommen, Sie müssen bestimmte Schriften, Stifte oder andere GDI-Objekte für das Drucken, aber nicht für die Bildschirmanzeige verwenden. Aufgrund des erforderlichen Arbeitsspeichers ist es ineffizient, diese Objekte beim Start der Anwendung zuzuordnen. Wenn die Anwendung gerade kein Dokument druckt, wird dieser Speicher möglicherweise für andere Zwecke benötigt. Es ist besser, sie bei Beginn des Druckens zuzuordnen und nach dem Druckvorgang zu löschen.

Um diese GDI-Objekte zuzuordnen, überschreiben Sie die [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) -Member-Funktion. Diese Funktion eignet sich aus zwei Gründen für diesen Zweck: das Framework ruft diese Funktion einmal am Anfang jedes Druckauftrags auf, und im Gegensatz zu [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)hat diese Funktion Zugriff auf das [CDC](../mfc/reference/cdc-class.md) -Objekt, das das Druckergerät darstellt. Trei. Sie können diese Objekte für die Verwendung während des Druckauftrags speichern, indem Sie Element Variablen in der Ansichts Klasse definieren, die auf GDI- `CFont *` Objekte verweisen (z. b. Member usw.).

Wenn Sie die von Ihnen erstellten GDI-Objekte verwenden möchten, wählen Sie Sie in der Element Funktion von [OnPrint](../mfc/reference/cview-class.md#onprint) in den Drucker Gerätekontext aus. Wenn Sie unterschiedliche GDI-Objekte für verschiedene Seiten des Dokuments benötigen, können Sie den `m_nCurPage` Member der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) -Struktur untersuchen und das GDI-Objekt entsprechend auswählen. Wenn Sie ein GDI-Objekt für mehrere aufeinanderfolgende Seiten benötigen, müssen Sie es bei jedem Aufrufen von `OnPrint` in den Gerätekontext wählen.

Um die Zuteilung dieser GDI-Objekte zu überschreiben, überschreiben Sie die [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) -Element Funktion. Das Framework ruft diese Funktion am Ende jedes Druckauftrags auf, wodurch Sie die Zuweisung druckspezifischer GDI-Objekte aufheben können, bevor die Anwendung zu anderen Aufgaben zurückkehrt.

## <a name="see-also"></a>Siehe auch

[Drucken](../mfc/printing.md)<br/>
[Funktionsweise des Standarddrucks](../mfc/how-default-printing-is-done.md)
