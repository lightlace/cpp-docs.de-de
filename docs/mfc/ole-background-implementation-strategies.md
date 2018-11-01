---
title: 'OLE-Hintergrund: Implementierungsstrategien'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
ms.openlocfilehash: a9bcbc16b08f16953df92efe5a83db39f9a33cc5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624392"
---
# <a name="ole-background-implementation-strategies"></a>OLE-Hintergrund: Implementierungsstrategien

Je nach Anwendung gibt es vier mögliche Implementierungsstrategien für das OLE-Unterstützung hinzufügen:

- Sie schreiben eine neue Anwendung.

   Diese Situation erfordert in der Regel den geringsten arbeiten. Sie führen Sie den Assistenten der MFC-Anwendung, und wählen Sie erweiterte Funktionen oder Unterstützung für Verbunddokumente eine Skelette-Anwendung erstellen. Informationen zu diesen Optionen und was sie tun, finden Sie im Artikel [erstellen eine MFC-EXE-Programm](../mfc/reference/mfc-application-wizard.md).

- Sie haben es sich um ein Programm geschrieben, mit der Microsoft Foundation Class-Bibliothek Version 2.0 oder höher, die keine OLE unterstützt.

   Erstellen einer neuen Anwendung mit der MFC-Anwendungs-Assistenten wie bereits erwähnt, und klicken Sie dann kopieren und fügen Sie den Code aus der neuen Anwendung in Ihre vorhandene Anwendung. Dies funktioniert für Server, Containern oder automatisierten Anwendungen. Finden Sie unter MFC [SCRIBBLE](../visual-cpp-samples.md) ein Beispiel für diese Strategie.

- Sie haben es sich um eine Microsoft Foundation Class Library-Programm, das OLE-Version 1.0-Unterstützung implementiert.

   Finden Sie unter [MFC technischer Hinweis 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) für diese Konvertierungsstrategie.

- Sie haben eine Anwendung, die nicht mithilfe der Microsoft Foundation Classes geschrieben wurde und möglicherweise oder möglicherweise keine Unterstützung von OLE implementiert haben.

   Diese Situation erfordert die meisten Aufgaben. Ein Ansatz besteht darin eine neue Anwendung erstellen, wie in der ersten Strategie, und kopieren Sie dann aus, und fügen den vorhandenen Code, auf. Wenn Ihr vorhandene Code in C# geschrieben ist, dann müssen Sie möglicherweise ändern, damit er als C++-Code kompiliert werden kann. Wenn Ihre C-Code über die Windows-API aufruft, müssen Sie nicht ändern, um die Microsoft Foundation Classes zu verwenden. Dieser Ansatz wahrscheinlich erfordert einige neustrukturierungen des Programms zur Unterstützung der Dokument-/Ansichtarchitektur verwendet, die für die Versionen 2.0 und höheren Versionen der Microsoft Foundation Classes. Weitere Informationen zu dieser Architektur, finden Sie unter [technischen Hinweis 25](../mfc/tn025-document-view-and-frame-creation.md).

Nachdem Sie eine Strategie entschieden haben, sollten Sie entweder Lesen der [Container](../mfc/containers.md) oder [Server](../mfc/servers.md) Artikel (je nach Art der Anwendung, die Sie schreiben), oder Überprüfen Sie die Beispielprogramme oder beides. Die MFC-OLE-Beispiele [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md) zeigen, wie Sie die verschiedenen Aspekte der Container und Server, implementieren. An verschiedenen Punkten in diesen Artikeln werden Sie bestimmte Funktionen in diesen Beispielen als Beispiele für die vorgestellten bezeichnet.

## <a name="see-also"></a>Siehe auch

[OLE-Hintergrund](../mfc/ole-background.md)<br/>
[Container: Implementieren eines Containers](../mfc/containers-implementing-a-container.md)<br/>
[Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)<br/>
[MFC-Anwendungs-Assistent](../mfc/reference/mfc-application-wizard.md)

