---
title: Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 412fa5c104d6e85bcaa6ba3703cc8c7ba535f25f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381208"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen
Die folgende Tabelle zeigt Ihre Rolle und das Framework OLE verlinken und Einbetten von Anwendungen erstellen. Diese repräsentieren die verfügbaren Optionen statt einer Sequenz von Schritten ausführen.  
  
### <a name="creating-ole-applications"></a>Erstellen von OLE-Serveranwendungen  
  
|Aufgabe|Sie tun|Das Framework ermöglicht|  
|----------|------------|------------------------|  
|Erstellen Sie eine COM-Komponente.|Führen Sie den MFC-Anwendung-Assistenten. Wählen Sie **Vollserver** oder **Miniserver** in der **Verbunddokumente** Registerkarte.|Das Framework generiert einen skelettanwendung mit COM-Komponente-Funktion aktiviert. Alle von der COM-Funktion kann an der vorhandenen Anwendung mit nur geringfügigen Änderungen übertragen werden.|  
|Erstellen Sie eine Steuerelementcontainer-Anwendung von Grund auf neu.|Führen Sie den MFC-Anwendung-Assistenten. Wählen Sie **Container** in der **Verbunddokumente** Registerkarte. Wechseln Sie mit der Klassenansicht mithilfe des auf den Quellcode-Editor. Geben Sie im Code für die COM-Handlerfunktionen.|Das Framework generiert eine Skelette-Anwendung, die COM-Objekten, die von COM-Komponente (Server)-Anwendungen erstellt eingefügt werden kann.|  
|Erstellen Sie eine Anwendung, die Automatisierung von Grund auf neu unterstützt.|Führen Sie den MFC-Anwendung-Assistenten. Wählen Sie **Automatisierung** aus der **erweiterte Funktionen** Registerkarte. Verwenden Sie Klassenansicht, um Methoden und Eigenschaften in der Anwendung für die Automatisierung verfügbar zu machen.|Das Framework generiert einen skelettanwendung, die aktiviert und von einer anderen Anwendung automatisiert werden kann.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)   
 [Reihenfolge der Operationen zur Erstellung von MFC-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Reihenfolge der Operationen zur Erstellung von ActiveX-Steuerelemente](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Reihenfolge der Operationen zur Erstellung Datenbankanwendungen](../mfc/sequence-of-operations-for-creating-database-applications.md)

