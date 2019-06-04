---
title: Zuordnen von GDI-Ressourcen
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: adfd8b19f683b82eec213890c8e1345e070ff3ec
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504629"
---
# <a name="allocating-gdi-resources"></a>Zuordnen von GDI-Ressourcen

In diesem Artikel wird beschrieben, wie Sie die für das Drucken benötigten Objekte der Windows-GDI (Graphics Device Interface) zuweisen und ihre Zuweisung aufheben.

> [!NOTE]
>  Weitere Informationen finden Sie unter den [GDI + SDK-Dokumentation](/windows/desktop/gdiplus/-gdiplus-gdi-start).

Angenommen, Sie müssen bestimmte Schriften, Stifte oder andere GDI-Objekte für das Drucken, aber nicht für die Bildschirmanzeige verwenden. Aufgrund des erforderlichen Arbeitsspeichers ist es ineffizient, diese Objekte beim Start der Anwendung zuzuordnen. Wenn die Anwendung gerade kein Dokument druckt, wird dieser Speicher möglicherweise für andere Zwecke benötigt. Es ist besser, sie bei Beginn des Druckens zuzuordnen und nach dem Druckvorgang zu löschen.

Um diese GDI-Objekte zuzuordnen, überschreiben die [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) Member-Funktion. Diese Funktion eignet sich gut für diesen Zweck aus zwei Gründen: das Framework ruft diese Funktion einmal zu Beginn jedes Druckauftrags und im Gegensatz zu [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), diese Funktion hat Zugriff auf die [CDC](../mfc/reference/cdc-class.md) Objekt, das den Druckertreiber darstellt. Sie können diese Objekte für die Verwendung während des Druckauftrags speichern, indem Sie das Definieren von Membervariablen in Ihrer Ansichtsklasse, die auf GDI-Objekte verweisen (z. B. `CFont *` Elemente usw.).

Um die GDI-Objekte verwenden Sie erstellt haben, wählen Sie diese für den Drucker-Gerätekontext in der [OnPrint](../mfc/reference/cview-class.md#onprint) Member-Funktion. Wenn Sie unterschiedliche GDI-Objekte für verschiedene Seiten des Dokuments benötigen, können Sie überprüfen die `m_nCurPage` Mitglied der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) strukturieren und das GDI-Objekt entsprechend wählen. Wenn Sie ein GDI-Objekt für mehrere aufeinanderfolgende Seiten benötigen, müssen Sie es bei jedem Aufrufen von `OnPrint` in den Gerätekontext wählen.

Um diese GDI-Objekte aufzuheben, überschreiben die [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) Member-Funktion. Das Framework ruft diese Funktion am Ende jedes Druckauftrags auf, wodurch Sie die Zuweisung druckspezifischer GDI-Objekte aufheben können, bevor die Anwendung zu anderen Aufgaben zurückkehrt.

## <a name="see-also"></a>Siehe auch

[Drucken](../mfc/printing.md)<br/>
[Funktionsweise des Standarddrucks](../mfc/how-default-printing-is-done.md)
