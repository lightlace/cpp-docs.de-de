---
title: Virtuelle Listensteuerelemente
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: b9da918017d300d7af61b1fd3ab27869e136bb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573671"
---
# <a name="virtual-list-controls"></a>Virtuelle Listensteuerelemente

Eine virtuelle Listenansicht-Steuerelement ist ein Listenansicht-Steuerelement, das die LVS_OWNERDATA-Format. Dieses Format können Sie die Möglichkeit der Unterstützung von bis zu eine Elementanzahl eine **DWORD** (standardelementanzahl nur erstreckt sich auch auf eine **Int**). Der größte Vorteil bereitgestellt, die durch dieses Format ist jedoch die Möglichkeit, nur eine Teilmenge der Daten im Arbeitsspeicher zu jedem Zeitpunkt. Dadurch können der virtuellen Listenansicht-Steuerelement, selbst für die Verwendung mit großen Datenbanken mit Informationen zu verleihen, in dem sind spezielle Methoden für den Zugriff auf Daten bereits vorhanden.

> [!NOTE]
>  Zusätzlich zur Bereitstellung von virtuellen Funktionen in `CListCtrl`, MFC bietet auch die gleiche Funktionalität in der [CListView](../mfc/reference/clistview-class.md) Klasse.

Es gibt einige Kompatibilitätsprobleme, die, denen Sie bei der Entwicklung virtuelle Listensteuerelemente bewusst sein sollten. Weitere Informationen finden Sie im Abschnitt "Kompatibilitätsproblemen" des Themas Listenansicht-Steuerelemente in das Windows SDK.

## <a name="handling-the-lvngetdispinfo-notification"></a>Behandeln der LVN_GETDISPINFO-Benachrichtigung

Virtuelle Listensteuerelemente verwalten nur sehr wenig Informationen. Mit Ausnahme von der Auswahl von Listenelementen und den Fokus wird die Informationen über die alle Elemente vom Besitzer des Steuerelements verwaltet. Informationen, die durch das Framework über eine benachrichtigungsmeldung LVN_GETDISPINFO angefordert wird. Um die angeforderten Informationen bereitzustellen, muss der Besitzer der das virtuelle Listenansicht-Steuerelement (oder das Steuerelement selbst) diese Benachrichtigung verarbeiten. Dies kann problemlos erfolgen mithilfe des Eigenschaftenfensters (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)). Der resultierende Code sollte in etwa wie im folgenden Beispiel aussehen (wobei `CMyDialog` besitzt das Steuerelementobjekt für virtuelle Listenansichten und behandelt das Dialogfeld wird die Benachrichtigung):

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

In den Handler für die Benachrichtigung LVN_GETDISPINFO müssen Sie prüfen, um festzustellen, welche Art von Informationen angefordert werden. Mögliche Werte sind:

- `LVIF_TEXT` Die *PszText* Member muss ausgefüllt werden.

- `LVIF_IMAGE` Die *iImage* Member muss ausgefüllt werden.

- `LVIF_INDENT` Die *iIndent* Member muss ausgefüllt werden.

- `LVIF_PARAM` Die *lParam* Member muss ausgefüllt werden. (Nicht für untergeordnete Elemente vorhanden Sie.)

- `LVIF_STATE` Die *Zustand* Member muss ausgefüllt werden.

Sie sollten dann angeben, an das Framework den Informationen angefordert werden.

Im folgende Beispiel (entnommen aus dem Text der Benachrichtigungshandler für das Steuerelement Listenobjekt) veranschaulicht eine mögliche Methode durch Angabe von Informationen für den Textpuffer und das Bild eines Elements:

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>Zwischenspeichern und virtuelle Listensteuerelemente

Da diese Art von Steuerelement für große Datasets vorgesehen ist, empfiehlt es sich, dass Sie die angeforderten Daten zur Verbesserung der Leistung der Abruf Zwischenspeichern. Das Framework bietet einen Mechanismus Cache-Abfragehinweise, bei der Optimierung des Caches durch Senden einer Benachrichtigung LVN_ODCACHEHINT.

Das folgende Beispiel aktualisiert den Cache mit dem Bereich, der an die Handlerfunktion übergeben.

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

Weitere Informationen zum Vorbereiten und Verwalten eines Caches finden Sie im Abschnitt "Verwaltung des Eigenschaftencache" des Themas Listenansicht-Steuerelemente in das Windows SDK.

## <a name="finding-specific-items"></a>Suchen von bestimmten Elementen

Die benachrichtigungsmeldung LVN_ODFINDITEM wird durch das virtuelle Listenansicht-Steuerelement gesendet, wenn es sich bei einem bestimmten Steuerelement ein Element gefunden werden muss. Die Benachrichtigung wird gesendet, wenn das Listenansicht-Steuerelement Key Schnellzugriff empfängt, oder beim Empfang einer Nachricht LVM_FINDITEM. Search-Informationen werden gesendet, in Form von ein **LVFINDINFO** -Struktur, die ein Member ist von der **NMLVFINDITEM** Struktur. Behandeln Sie diese Meldung durch Überschreiben der `OnChildNotify` -Funktion von der Liste Objekt zu steuern, und überprüfen Sie im Text des Handlers, für die Nachricht LVN_ODFINDITEM. Wenn gefunden, die entsprechende Aktion ausgeführt.

Sie sollten darauf vorbereitet, die für ein Element zu suchen, die von der Listenansicht-Steuerelement Informationen übereinstimmt, sein. Sie sollten den Index des Elements, wenn erfolgreich, oder -1 zurückgeben, wenn kein übereinstimmendes Element gefunden wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

