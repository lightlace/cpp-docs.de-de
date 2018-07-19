---
title: 'Automatisierungsclients: Verwenden von Typbibliotheken | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MkTypLib
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- dispatch class [MFC]
- Automation clients, type libraries
- type libraries, Automation clients
- ODL (Object Description Language)
- ODL files
- classes [MFC], dispatch
- MkTypLib tool
- .odl files
ms.assetid: d405bc47-118d-4786-b371-920d035b2047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67fa0f5d164ae325caff576fb41695fc8689fda0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342588"
---
# <a name="automation-clients-using-type-libraries"></a>Automatisierungsclients: Verwenden von Typbibliotheken
Benutzeroberflächenautomatisierungs-Clients benötigen Informationen zum Server-Objekte Eigenschaften und Methoden, wenn die Clients sind, um die Server Objekte zu bearbeiten. Datentypen weisen Eigenschaften auf. Methoden werden häufig Rückgabewerte und Parameter annehmen. Der Client benötigt Informationen zu den Datentypen all dieser um statisch in Server-Objekt zu binden.  
  
 Diese Typinformationen kann auf verschiedene Weise bekannte vorgenommen werden. Die empfohlene Vorgehensweise besteht darin eine Typbibliothek zu erstellen.  
  
 Informationen zu [MkTypLib](http://msdn.microsoft.com/library/windows/desktop/aa366797), finden Sie im Windows SDK.  
  
 Visual C++ kann eine Typbibliothek-Datei gelesen, und erstellen Sie eine Dispatchklasse abgeleitet [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md). Ein Objekt dieser Klasse enthält Eigenschaften und Vorgänge, die denen des Serverobjekts duplizieren. Die Anwendung aufruft, Eigenschaften und Vorgänge des Objekts und Funktionalität von geerbten `COleDispatchDriver` leitet diese Aufrufe für das OLE-System, der wiederum diese auf das Serverobjekt weiterleitet.  
  
 Visual C++ verwaltet diese Typbibliothek-Datei automatisch für Sie, wenn Sie ausgewählt haben, Automatisierung eingeschlossen, wenn das Projekt erstellt wurde. TLB-Datei werden im Rahmen des jeden Build wird mit MkTypLib erstellt.  
  
### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>So erstellen Sie eine Dispatch-Klasse aus einer Typbibliotheksdatei (.tlb)  
  
1.  Klicken Sie in der Klassenansicht oder Projektmappen-Explorer, mit der rechten Maustaste des Projekts, und klicken Sie auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen** im Kontextmenü.  
  
2.  In der **Klasse hinzufügen** wählen Sie im Dialogfeld die **Visual c++ c++ / MFC** Ordner im linken Bereich. Wählen Sie die **MFC-Klassen aus der Typbibliothek** Symbol aus dem rechten Bereich und auf **öffnen**.  
  
3.  In der **Assistenten zum Hinzufügen von Klassen aus der Typbibliothek** Dialogfeld wählen eine Typbibliothek aus der **verfügbaren Typbibliotheken** Dropdown-Liste. Die **Schnittstellen** Feld zeigt die Schnittstellen für die ausgewählte Typbibliothek verfügbar sind.  
  
    > [!NOTE]
    >  Sie können die Schnittstellen aus mehr als eine Typbibliothek auswählen.  
  
     Wählen die Schnittstellen, doppelklicken darauf, oder klicken Sie auf die **hinzufügen** Schaltfläche. Wenn Sie dies tun, Namen für die Dispatchklassen werden in der **generierte Klassen** Feld. Sie können die Klassennamen in Bearbeiten der `Class` Feld.  
  
     Die **Datei** Feld zeigt die Datei, die in der Klasse deklariert werden. (Sie können auch diesen Namen bearbeiten). Sie können die Schaltfläche zum Durchsuchen auch andere Dateien auszuwählen, wenn Sie es vorziehen, die Informationen über Header und Implementierung in vorhandene Dateien oder in einem anderen Projektverzeichnis Verzeichnis geschrieben haben.  
  
    > [!NOTE]
    >  Die Dispatchklassen für die ausgewählten Schnittstellen werden in der hier angegebenen Datei abgelegt werden. Gegebenenfalls die Schnittstellen in separaten Header deklariert werden, müssen Sie diesen Assistenten für jeden Header-Datei ausführen, die Sie erstellen möchten.  
  
    > [!NOTE]
    >  Einige Informationen in der Typbibliothek kann in Dateien gespeichert werden. DLL. OCX, oder. Erweiterungen der OLB-Datei.  
  
4.  Klicken Sie auf **Fertig stellen**.  
  
     Der Assistent wird dann den Code für Ihre Dispatchklassen, die mithilfe der angegebenen Klasse und den Dateinamen geschrieben.  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisierungsclients](../mfc/automation-clients.md)

