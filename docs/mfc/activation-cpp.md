---
title: Aktivierung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0f6207d91fa3816ab17462f62bd39551f7961e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383973"
---
# <a name="activation-c"></a>Aktivierung (C++)

Dieser Artikel beschreibt die Rolle der Aktivierung in die visuelle Bearbeitung von OLE-Elementen. Nachdem ein Benutzer ein OLE-Element in einem Containerdokument eingebettet ist, müssen sie möglicherweise verwendet werden. Zu diesem Zweck doppelklickt der Benutzer das Element, das dieses Element aktiviert wird. Die am häufigsten Aktivität für die Aktivierung bearbeitet wird. Viele aktuelle OLE-Elemente, wenn für die Bearbeitung aktiviert dazu führen, dass die Menüs und Symbolleisten im aktuellen Frame Fenster so ändern Sie entsprechend die Attribute für die Serveranwendung, die das Element erstellt hat. Dieses Verhalten, bekannt als direkte Aktivierung ermöglicht die Benutzer, ein eingebettetes Element in einem Verbunddokument bearbeiten, ohne Container Dokumentenfenster verlassen zu müssen.

Es ist auch möglich, die eingebettete OLE-Elemente in einem separaten Fenster zu bearbeiten. Dies geschieht, wenn der Container oder der Server die direkte Aktivierung nicht unterstützt. In diesem Fall, wenn der Benutzer ein eingebettetes Element doppelklickt, die Serveranwendung in einem separaten Fenster gestartet wird und das eingebettete Element wird als eigenes Dokument angezeigt. Der Benutzer das Element in diesem Fenster bearbeitet wird. Wenn Bearbeitung abgeschlossen ist, wird der Benutzer schließt die Serveranwendung und der containeranwendung zurückgegeben.

Als Alternative können wahlweise kann der Benutzer "öffnen, bearbeiten" mit der  **\<Objekt > Öffnen** Befehl die **bearbeiten** Menü. Dadurch wird das Objekt in einem separaten Fenster geöffnet.

> [!NOTE]
>  Bearbeiten die eingebetteten Elemente in einem separaten Fenster war das Standardverhalten in Version 1 von OLE, und einige OLE-Anwendungen unterstützen möglicherweise nur diese Art der Bearbeitung.

Direkte Aktivierung wird einen dokumentorientierte Ansatz zum Erstellen eines Dokuments. Der Benutzer kann als einzelne Entität, einem Verbunddokument behandeln ohne Wechseln zwischen Anwendungen arbeiten. Direkte Aktivierung wird jedoch nur für eingebettete Elemente, nicht für verknüpfte Elemente verwendet: sie müssen in einem separaten Fenster bearbeitet werden. Dies ist, da ein verknüpftes Element tatsächlich in einem anderen Ort gespeichert werden. Die Bearbeitung der ein verknüpftes Element findet innerhalb der Daten, d. h. der tatsächliche Kontext, in denen die Daten gespeichert werden. Bearbeiten ein verknüpftes Element in einem separaten Fenster erinnert sich den Benutzer, den die Daten zu einem anderen Dokument gehören.

MFC unterstützt keine geschachtelten direkten Aktivierung. Wenn Sie eine Container/Server-Anwendung erstellen, und, dass Container/Server in einem anderen Container und direkt aktiviert eingebettet ist, es kein direktes aktivieren eingebettete Objekte.

Was auf ein eingebettetes Element geschieht, wenn der Benutzer es doppelklickt, hängt von der Verben, die für das Element definiert. Weitere Informationen finden Sie unter [Aktivierung: Verben](../mfc/activation-verbs.md).

## <a name="see-also"></a>Siehe auch

[OLE](../mfc/ole-in-mfc.md)<br/>
[Container](../mfc/containers.md)<br/>
[Server](../mfc/servers.md)

