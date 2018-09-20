---
title: Erstellen eines nicht modalen Eigenschaftenblatts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16b0a558dcae7d2bf35cf530abfea15ef6f8138a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378097"
---
# <a name="creating-a-modeless-property-sheet"></a>Erstellen eines nicht modalen Eigenschaftenblatts

Normalerweise werden der Eigenschaftenblätter, die Sie erstellen gebunden sein. Wenn Sie ein modales Eigenschaftsblatt verwenden zu können, muss der Benutzer vor der Verwendung von anderen Teilen der Anwendung zu schließen. Dieser Artikel beschreibt die Methoden, mit denen, die Sie ein nicht modalen Eigenschaftenblatts zu erstellen, das dem Benutzer ermöglicht, das Eigenschaftenfenster geöffnet bleibt, bei der Verwendung von anderen Teilen der Anwendung verwenden können.

Rufen Sie zum Anzeigen von einem Eigenschaftenblatt als ein nicht modales Dialogfeld statt als modales Dialogfeld [CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create) anstelle von [DoModal](../mfc/reference/cpropertysheet-class.md#domodal). Sie müssen auch einige zusätzliche Aufgaben zur Unterstützung eines nicht modalen Eigenschaftenblatts implementieren.

Eine zusätzliche Aufgaben ist die Datenaustausch zwischen dem Eigenschaftenblatt und das externe Objekt an, die geändert werden, wenn das Eigenschaftenfenster geöffnet ist. Dies ist normalerweise die gleiche Aufgabe wie standard nicht modale Dialogfelder. Teil dieser Aufgabe ist die Implementierung von eines Kanals für die Kommunikation zwischen den nicht modalen Eigenschaftenblatts und das externe Objekt, das auf dem die Einstellungen der Eigenschaft angewendet werden. Diese Implementierung ist viel einfacher, wenn Sie beim Ableiten einer Klasse von [CPropertySheet](../mfc/reference/cpropertysheet-class.md) für Ihre nicht modalen Eigenschaftenblatts. In diesem Artikel wird davon ausgegangen, dass dies geschehen ist.

Eine Methode für die Kommunikation zwischen den nicht modalen Eigenschaftenblatts und das externe Objekt (die aktuelle Auswahl in einer Sicht, z. B.) ist, um einen Zeiger aus dem Eigenschaftenblatt auf das externe Objekt zu definieren. Definieren Sie eine Funktion (z. B. `SetMyExternalObject`) in der `CPropertySheet`-abgeleitete Klasse, um den Zeiger zu ändern, bei jeder Änderung des Fokus von einem externen Objekt in einen anderen. Die `SetMyExternalObject` Funktion benötigt, um die Einstellungen für jede Eigenschaftsseite auf das neu ausgewählte externe Objekt entsprechend zurückzusetzen. Zu diesem Zweck die `SetMyExternalObject` Funktion muss in der Lage, Zugriff auf die [CPropertyPage](../mfc/reference/cpropertypage-class.md) Objekte für die `CPropertySheet` Klasse.

Ist am einfachsten Zugriff auf die Eigenschaftenseiten in einem Eigenschaftenblatt Einbetten der `CPropertyPage` Objekte in der `CPropertySheet`-abgeleitetes Objekt. Einbetten von `CPropertyPage` Objekte in der `CPropertySheet`-abgeleitetes Objekt unterscheidet sich von der typischen Entwurf für modale Dialogfelder, in dem der Besitzer des Eigenschaftenblatts erstellt die `CPropertyPage` Objekte und übergibt sie an das Eigenschaftenblatt über [ CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage).

Es gibt viele Benutzeroberfläche alternativen, um zu bestimmen, wenn die Einstellungen des nicht modalen Eigenschaftenblatts an ein externes Objekt angewendet werden soll. Eine Alternative besteht, wenden Sie die Einstellungen der aktuellen Seite ein, wenn der Benutzer einen beliebigen Wert ändert. Eine weitere Möglichkeit ist eine Schaltfläche "anwenden" bereitgestellt, die dem Benutzer ermöglicht, Änderungen in den Eigenschaftenseiten zu sammeln, bevor ein Commit auf das externe Objekt. Informationen zu Methoden zum Behandeln der Schaltfläche "anwenden" finden Sie im Artikel [behandeln die Schaltfläche "anwenden"](../mfc/handling-the-apply-button.md).

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)<br/>
[Datenaustausch](../mfc/exchanging-data.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

