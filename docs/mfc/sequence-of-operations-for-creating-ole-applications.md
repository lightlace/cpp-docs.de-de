---
title: Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen | Microsoft-Dokumentation
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
ms.openlocfilehash: 02542f8a4eb382ff4d7a88f98163b0052be09f75
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392511"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen

Die folgende Tabelle zeigt Ihre Rolle und des Frameworks, bei der Erstellung von OLE zu verlinken und Einbetten von Anwendungen. Diese repräsentieren die verfügbaren Optionen statt einer Sequenz von Schritten ausführen.

### <a name="creating-ole-applications"></a>OLE-Anwendungen erstellen

|Aufgabe|Sie tun|Das Framework ermöglicht|
|----------|------------|------------------------|
|Erstellen Sie eine COM-Komponente.|Führen Sie den Assistenten zum MFC-Anwendungen. Wählen Sie **Vollserver** oder **Mini-Servers** in die **Verbunddokumente** Registerkarte.|Das Framework generiert eine Skelette-Anwendung mit COM-Komponente-Funktion aktiviert. Alle COM-Funktion kann auf die vorhandene Anwendung mit nur geringfügigen Änderungen übertragen werden.|
|Erstellen Sie eine containeranwendung von Grund auf neu.|Führen Sie den Assistenten zum MFC-Anwendungen. Wählen Sie **Container** in die **Verbunddokumente** Registerkarte. Fahren Sie mit der Verwendung der Klassenansicht, mit dem Quellcode-Editor. Geben Sie Code für die COM-Handlerfunktionen.|Das Framework generiert eine Skelette-Anwendung, die COM-Objekte, die von COM-Komponente (Server)-Anwendungen erstellt einfügen können.|
|Erstellen Sie eine Anwendung, die Automatisierung von Grund auf neu unterstützt.|Führen Sie den Assistenten zum MFC-Anwendungen. Wählen Sie **Automation** aus der **erweiterte Features** Registerkarte. Mithilfe der Klassenansicht, um Methoden und Eigenschaften in Ihrer Anwendung für die Automatisierung verfügbar zu machen.|Das Framework generiert eine Skelette-Anwendung, die aktiviert und von anderen Anwendungen automatisiert werden kann.|

## <a name="see-also"></a>Siehe auch

[Erstellen im Framework](../mfc/building-on-the-framework.md)<br/>
[Reihenfolge der Operationen zur Erstellung von MFC-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[Operationssequenz zur Erstellung von ActiveX-Steuerelementen](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[Reihenfolge der Operationen zur Erstellung Datenbankanwendungen](../mfc/sequence-of-operations-for-creating-database-applications.md)

