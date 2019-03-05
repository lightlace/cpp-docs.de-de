---
title: 'Beispiel für Active Document-Container: Office Sammelmappen'
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
ms.openlocfilehash: b06bc0f22ee71c8afbbc8feadca68895fc24a50b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279184"
---
# <a name="example-of-active-document-containment-office-binder"></a>Beispiel für Active Document-Container: Office Sammelmappen

Der Microsoft Office Binder ist ein Beispiel für einen active Document-Container. Ein Office Binder Hauptbereiche zwei, wie Container in der Regel der Fall ist. Der linke Bereich enthält die Symbole, die aktive Dokumente in der Binder entsprechen. Jedes Dokument wird aufgerufen, eine *Abschnitt* innerhalb der Binder. Ein Binder kann z. B. Word-Dokumente, PowerPoint-Dateien, Excel-Kalkulationstabellen usw. enthalten.

Klicken auf ein Symbol im linken Bereich klicken, wird das entsprechende active Document aktiviert. Im rechten Bereich des Binders zeigt den Inhalt des aktuell ausgewählten aktiven Dokuments.

Wenn Sie öffnen, und aktivieren ein Word-Dokument in einen Binder, die Word-Menü- und Symbolleisten angezeigt werden, am oberen Rand die Ansichtsframe und Sie können die Inhalte des Dokuments mit einem Word-Befehl oder Tool bearbeiten. Allerdings ist die Menüleiste eine Kombination aus der der Bindung und die Word Menüleisten. Da sowohl Binder als Word auch **Hilfe** Menüs, den Inhalt der jeweiligen Menüs zusammengeführt werden. Active Document-Container, z. B. Office Binder automatisch bereitstellen **Hilfe** Menü zusammengeführt; Weitere Informationen finden Sie [Zusammenführen von Hilfemenüs](../mfc/help-menu-merging.md).

Wenn Sie auswählen ein aktiven Dokuments von einer anderen den Typ des Binders Änderungen an der Benutzeroberfläche auf dem der Anwendungstyp für das aktive Dokument Rechnung zu tragen. Z. B. ein Binder für ein Excel-Arbeitsblatt enthält, werden Sie feststellen, dass Menüs in der Binder ändern, wenn Sie im Abschnitt der Excel-Arbeitsblatt auswählen.

Es gibt natürlich anderen möglichen Arten von Containern neben Binder. Datei-Explorer verwendet die typische zweiteiligen-Schnittstelle, die in der im linke Bereich ein Strukturansicht-Steuerelement verwendet, um eine hierarchische Liste von Verzeichnissen in einem Laufwerk oder im Netzwerk angezeigt wird, während der rechte Bereich enthaltenen Dateien im ausgewählten Verzeichnis zeigt. Internet-Browser nach der Art eines Container (z. B. Microsoft Internet Explorer), anstatt über eine Dual-Bereich-Schnittstelle, in der Regel verfügt über ein einzelnes Frame und Navigation über die Links enthält.

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containment.md)
