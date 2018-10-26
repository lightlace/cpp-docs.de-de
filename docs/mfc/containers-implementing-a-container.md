---
title: 'Container: Implementieren eines Containers | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28c93e5d1331d7195b894fe88c3fe5fc11e7c31d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074071"
---
# <a name="containers-implementing-a-container"></a>Container: Implementieren eines Containers

Dieser Artikel fasst das Verfahren zum Implementieren eines Containers und verweist auf den anderen Artikeln, die ausführlichere erläuterungen zum Implementieren von Containern bereitstellen. Außerdem werden einige optionale OLE-Funktionen, die Sie implementieren möchten, und die Artikel beschreiben diese Funktionen aufgeführt.

#### <a name="to-prepare-your-cwinapp-derived-class"></a>So bereiten Sie Ihre CWinApp abgeleitete Klasse vor.

1. Initialisieren die OLE-Bibliotheken durch Aufrufen `AfxOleInit` in die `InitInstance` Member-Funktion.

1. Rufen Sie `CDocTemplate::SetContainerInfo` in `InitInstance` das Menü und der Zugriffstaste zuweisen Ressourcen verwendet, wenn ein eingebettetes Element direkt aktiviert. Weitere Informationen zu diesem Thema finden Sie unter [Aktivierung](../mfc/activation-cpp.md).

Diese Funktionen werden automatisch für Sie bereitgestellt, bei der Verwendung der MFC-Anwendung-Assistent zum Erstellen einer containeranwendung. Finden Sie unter [erstellen ein MFC-EXE-Programm](../mfc/reference/mfc-application-wizard.md).

#### <a name="to-prepare-your-view-class"></a>So bereiten Sie Ihre Ansichtsklasse vor

1. Die Verwaltung von ausgewählten Elementen mithilfe eines Zeigers oder eine Liste von Zeigern auf, wenn Sie die Auswahl von mehreren, auf die ausgewählten Elemente unterstützen. Ihre `OnDraw` Funktion muss alle OLE-Elemente zeichnen.

1. Außer Kraft setzen `IsSelected` zu überprüfen, ob das Element, das an sie übergebenen derzeit ausgewählt ist.

1. Implementieren einer `OnInsertObject` Message-Handler zum Anzeigen der **Objekt einfügen** Dialogfeld.

1. Implementieren einer `OnSetFocus` Message-Handler, der Fokus aus der Ansicht auf ein direktes active OLE zu übertragen, eingebettete Element.

1. Implementieren einer `OnSize` informiert eine OLE-Message-Handler eingebettete Element, dass das Rechteck entsprechend ändern der Größe der enthaltenen Ansicht geändert werden muss.

Da die Implementierung dieser Funktionen erheblich von einer Anwendung zur nächsten variiert, stellt der Anwendungs-Assistent nur eine einfache Implementierung bereit. Sie müssen wahrscheinlich zum Anpassen dieser Funktionen rufen Sie Ihre Anwendung ordnungsgemäß funktioniert. Ein Beispiel hierfür finden Sie unter den [CONTAINER](../visual-cpp-samples.md) Beispiel.

#### <a name="to-handle-embedded-and-linked-items"></a>Eingebettete und verknüpfte Elemente verarbeitet werden

1. Leiten Sie eine Klasse von [COleClientItem](../mfc/reference/coleclientitem-class.md). Objekte dieser Klasse stellen die Elemente, die in eingebettet oder in Ihr Dokument OLE verknüpft wurden dar.

1. Außer Kraft setzen `OnChange`, `OnChangeItemPosition`, und `OnGetItemPosition`. Diese Funktionen verarbeiten, Ändern der Größe und Positionierung eingebettete und verknüpfte Elemente zu ändern.

Der Anwendungs-Assistent wird zum Ableiten der Klasse für Sie allerdings müssen Sie wahrscheinlich überschreiben `OnChange` und anderen Funktionen, die mit in Schritt 2 im vorangegangenen Verfahren aufgeführt. Die Skelett-Implementierungen müssen für die meisten Anwendungen angepasst werden, da diese Funktionen aus einer Anwendung in den nächsten unterschiedlich implementiert sind. Dieser Beispiele finden Sie in den MFC-Beispielen [DRAWCLI](../visual-cpp-samples.md) und [CONTAINER](../visual-cpp-samples.md).

Sie müssen eine Anzahl von Elementen der containeranwendung Menüstruktur zur Unterstützung von OLE hinzufügen. Weitere Informationen dazu finden Sie unter [Menüs und Ressourcen: Containererweiterungen](../mfc/menus-and-resources-container-additions.md).

Möglicherweise möchten Sie auch einige der folgenden Funktionen in Ihrer Anwendung mit Containern zu unterstützen:

- Direkte Aktivierung, wenn Sie ein eingebettetes Element zu bearbeiten.

   Weitere Informationen finden Sie unter [Aktivierung](../mfc/activation-cpp.md).

- Erstellung von OLE Elemente per Drag & Drop eine Auswahl aus einer Serveranwendung.

   Weitere Informationen finden Sie unter [Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md).

- Enthält Links zu eingebetteten Objekten oder Kombination aus Container/Server-Anwendungen.

   Weitere Informationen finden Sie unter [Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md).

## <a name="see-also"></a>Siehe auch

[Container](../mfc/containers.md)<br/>
[Container: Clientelemente](../mfc/containers-client-items.md)

