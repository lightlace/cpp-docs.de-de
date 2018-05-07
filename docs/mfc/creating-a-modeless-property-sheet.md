---
title: Erstellen eines nicht modalen Eigenschaftenblatts | Microsoft Docs
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
ms.openlocfilehash: 10dbef813d922bd01a5f9215b6d6e642349d2b75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-modeless-property-sheet"></a>Erstellen eines nicht modalen Eigenschaftenblatts
Normalerweise werden der Eigenschaftenblätter, die Sie erstellen gebunden sein. Wenn Sie ein modales Eigenschaftenblatt verwenden, muss der Benutzer Eigenschaftenblatt schließen, bevor mit einem beliebigen anderen Teil der Anwendung. Dieser Artikel beschreibt die Methoden beschrieben, die Sie verwenden können, um eines nicht modalen Eigenschaftenblatts zu erstellen, das dem Benutzer ermöglicht, das Eigenschaftenfenster geöffnet bleibt, andere Teile der Anwendung.  
  
 Um ein Eigenschaftenblatt als ein nicht modales Dialogfeld statt als modales Dialogfeld anzuzeigen, rufen [CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create) anstelle von [DoModal](../mfc/reference/cpropertysheet-class.md#domodal). Sie müssen auch einige zusätzlichen Aufgaben zur Unterstützung eines nicht modalen Eigenschaftenblatts implementieren.  
  
 Eine zusätzliche Aufgaben ist Datenaustausch zwischen dem Eigenschaftenblatt und einem externen Objekt, das sie geändert wird, wenn das Eigenschaftenfenster geöffnet ist. Dies ist in der Regel die gleiche Aufgabe wie für standard nicht modale Dialogfelder. Teil dieser Aufgabe wird ein Kommunikationskanal zwischen dem nicht modalen Eigenschaftenblatts und das externe Objekt, für das die eigenschafteneinstellungen gelten, implementiert. Diese Implementierung ist wesentlich einfacher, wenn Sie beim Ableiten einer Klasse von [CPropertySheet](../mfc/reference/cpropertysheet-class.md) für Ihre nicht modalen Eigenschaftenblatts. In diesem Artikel wird davon ausgegangen, dass Sie getan haben.  
  
 Eine Methode für die Kommunikation zwischen den nicht modalen Eigenschaftenblatts und externe Objekt (die aktuelle Auswahl in einer Ansicht, z. B.) besteht darin, einen Zeiger aus dem Eigenschaftenblatt auf das externe Objekt definieren. Eine Funktion definieren (z. B. `SetMyExternalObject`) in der `CPropertySheet`-abgeleitete Klasse, um den Zeiger zu ändern, bei jeder Änderung des Fokus von einem externen Objekt zu einem anderen. Die `SetMyExternalObject` Funktion benötigt, um die Einstellungen für jede Eigenschaftsseite auf die neu ausgewählte externe Objekt entsprechend zurückzusetzen. Um dies zu erreichen der `SetMyExternalObject` Funktion muss in der Lage, Zugriff auf die [CPropertyPage](../mfc/reference/cpropertypage-class.md) Objekte für die `CPropertySheet` Klasse.  
  
 Ist die einfachste Möglichkeit für den Zugriff auf die Eigenschaftenseiten in einem Eigenschaftenblatt Einbetten der `CPropertyPage` Objekte in der `CPropertySheet`-abgeleitetes Objekt. Einbetten von `CPropertyPage` Objekte in der `CPropertySheet`-abgeleitete Objekt unterscheidet sich von der typischen Entwurf für modale Dialogfelder, in dem der Besitzer des Eigenschaftenblatts erstellt die `CPropertyPage` -Objekte und übergibt sie an das Eigenschaftenblatt über [ CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage).  
  
 Es gibt viele Benutzeroberfläche Alternativen zu bestimmen, wann die Einstellungen von der nicht modalen Eigenschaftenblatts auf ein externes Objekt angewendet werden soll. Eine Alternative besteht, wenden die Einstellungen der aktuellen Seite aus, wenn der Benutzer einen beliebigen Wert ändert. Eine Alternative ist eine Schaltfläche "anwenden" bereitgestellt werden, die dem Benutzer ermöglicht, die Änderungen auf den Eigenschaftenseiten kumuliert werden vor dem bestätigen sie auf das externe Objekt. Informationen zu Methoden zum Behandeln der Schaltfläche "anwenden" finden Sie im Artikel [behandeln die Schaltfläche "anwenden"](../mfc/handling-the-apply-button.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)   
 [Austauschen von Daten](../mfc/exchanging-data.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

