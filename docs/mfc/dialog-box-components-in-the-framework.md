---
title: Dialogfeld-Steuerelemente im Framework | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6936a48d1a3e1845d56c73524c84800d9d605155
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065505"
---
# <a name="dialog-box-components-in-the-framework"></a>Dialogfeld-Steuerelemente im Framework

In der MFC-Framework besteht ein Dialogfeld, das aus zwei Komponenten:

- Eine Dialogfeldvorlagen-Ressource, die das Dialogfeld-Steuerelemente und die Position angibt.

   Die Ressource speichert eine Dialogfeldvorlage aus der Windows das Dialogfeld erstellt werden soll, und zeigt ihn an. Die Vorlage gibt das Dialogfeld Eigenschaften, einschließlich, seine Größe, Position, Stil, und die Typen und Positionen der Steuerelemente für das Dialogfeld. Verwenden Sie in der Regel eine Dialogfeldvorlage als Ressource gespeichert, aber Sie können auch Ihre eigene Vorlage erstellen, im Arbeitsspeicher.

- Eine Dialogfeldklasse, aus abgeleiteten [CDialog](../mfc/reference/cdialog-class.md), um eine programmgesteuerte Schnittstelle für die Verwaltung das Dialogfeld zu gewähren.

   Ein Dialogfeld, das ist ein Fenster, und es wird in einem Windows-Fenster, wenn es sichtbar angefügt werden. Wenn das Dialogfeld erstellt wird, wird der Dialogfeldvorlagen-Ressource als Vorlage zum Erstellen von untergeordneten Fenstersteuerelemente für das Dialogfeld.

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

