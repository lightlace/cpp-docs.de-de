---
title: 'OLE-Hintergrund: Implementierungsstrategien | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe15690b50c9398d660ca53effbec23cc35f49e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ole-background-implementation-strategies"></a>OLE-Hintergrund: Implementierungsstrategien
Es gibt vier mögliche Strategien zum Hinzufügen von OLE-Unterstützung, je nach Ihrer Anwendung:  
  
-   Schreiben Sie eine neue Anwendung.  
  
     Diese Situation erfordert in der Regel den geringsten arbeiten. Führen Sie den Assistenten der MFC-Anwendung, und wählen Sie erweiterte Funktionen oder Verbunddokumente auf, um eine skelettanwendung zu erstellen. Informationen zu diesen Optionen und was sie tun, finden Sie im Artikel [Erstellen einer MFC-EXE-Programm](../mfc/reference/mfc-application-wizard.md).  
  
-   Sie haben ein Programm mit der Microsoft Foundation Class-Bibliothek Version 2.0 oder höher, das keine OLE unterstützt geschrieben wurden.  
  
     Erstellen Sie eine neue Anwendung mit der MFC-Anwendungs-Assistenten wie bereits erwähnt, und klicken Sie dann kopieren Sie und fügen Sie den Code in die neue Anwendung in einer vorhandenen Anwendung. Diese Methode kann für Server, Container und automatisierten Anwendungen verwendet. Finden Sie unter MFC [SCRIBBLE](../visual-cpp-samples.md) ein Beispiel für diese Strategie.  
  
-   Sie haben ein Microsoft Foundation Class Library-Programm, das OLE-Version 1.0-Unterstützung implementiert.  
  
     Finden Sie unter [MFC technischer Hinweis 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) für diese Konvertierungsstrategie.  
  
-   Sie haben eine Anwendung, die nicht mithilfe der Microsoft Foundation Classes geschrieben wurde, und kann oder möglicherweise keine OLE-Unterstützung implementiert haben.  
  
     Diese Situation ist die meiste Arbeit erforderlich. Ein besteht Ansatz darin, eine neue Anwendung erstellen, wie in der ersten Strategie, und klicken Sie dann kopieren und fügen den vorhandenen Code hinein. Wenn Sie der vorhandene Code in C# geschrieben ist, müssen Sie es ändern, sodass er als C++-Code kompilieren kann. Wenn die C-Code der Windows-API aufgerufen wird, müssen Sie nicht ändern, um die Microsoft Foundation-Klassen zu verwenden. Dieser Ansatz wahrscheinlich benötigen einige Umstrukturierung des Programms zur Unterstützung der Dokument-/Ansichtarchitektur von Versionen 2.0 und höheren Versionen der Microsoft Foundation Classes verwendet werden. Weitere Informationen zu dieser Architektur, finden Sie unter [technischen Hinweis 25](../mfc/tn025-document-view-and-frame-creation.md).  
  
 Nachdem Sie eine Strategie entschieden haben, sollten Sie entweder Lese-der [Container](../mfc/containers.md) oder [Server](../mfc/servers.md) Artikel (je nach Typ der Anwendung, die Sie schreiben), oder Überprüfen Sie die Beispielprogramme oder beides. MFC-OLE-Beispielen [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md) zeigen, wie die verschiedenen Aspekte der Container und Server, bzw. zu implementieren. An verschiedenen Punkten in der gesamten in diesen Artikeln werden bestimmte Funktionen in diesen Beispielen als Beispiele für die gerade beschriebenen Verfahren bezeichnet.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE-Hintergrund](../mfc/ole-background.md)   
 [Container: Implementieren eines Containers](../mfc/containers-implementing-a-container.md)   
 [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)   
 [MFC-Anwendungs-Assistent](../mfc/reference/mfc-application-wizard.md)

