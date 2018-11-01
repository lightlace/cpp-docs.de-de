---
title: 'Automatisierungsclients: Verwenden von Typbibliotheken'
ms.date: 11/04/2016
f1_keywords:
- MkTypLib
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
ms.openlocfilehash: bd11bd8f2666bb2c211f7abe93d473f466963bd6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437049"
---
# <a name="automation-clients-using-type-libraries"></a>Automatisierungsclients: Verwenden von Typbibliotheken

Benutzeroberflächenautomatisierungs-Clients benötigen Informationen zu Eigenschaften und Methoden von Server-Objekte, wenn die Clients sind, die Server Objekte zu bearbeiten. Datentypen weisen Eigenschaften auf. Methoden werden häufig Rückgabewerte und Parameter akzeptieren. Der Client benötigt Informationen zu den Datentypen, der alle diese zum statisch in Server-Objekt zu binden.

Diese Typinformationen kann auf verschiedene Weise bekannte vorgenommen werden. Die empfohlene Methode ist die Erstellung eine Typbibliothek.

Informationen zum [MkTypLib](/windows/desktop/Midl/differences-between-midl-and-mktyplib), finden Sie im Windows SDK.

Visual C++ kann eine Typbibliothek-Datei zu lesen und erstellen Sie eine Dispatchklasse abgeleitet [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md). Ein Objekt dieser Klasse verfügt über Eigenschaften und Operationen des Serverobjekts diese duplizieren. Die Anwendung aufruft, Eigenschaften und Operationen des Objekts und Funktionalität von geerbten `COleDispatchDriver` leitet diese Aufrufe für das OLE-System, der diese wiederum auf das Serverobjekt weiterleitet.

Visual C++ verwaltet diese Typbibliothek-Datei automatisch für Sie, wenn Sie Automation einbeziehen, wenn es sich bei der Erstellung des Projekts ausgewählt haben. Im Rahmen jedes Builds wird die TLB-Datei mit MkTypLib erstellt werden.

### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>Erstellen eine Dispatchklasse aus einem Typbibliotheksdatei (.tlb)

1. Klicken Sie in der Klassenansicht oder Projektmappen-Explorer, mit der rechten Maustaste in des Projekts, und klicken Sie auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen** im Kontextmenü auf.

1. In der **Klasse hinzufügen** wählen Sie im Dialogfeld die **Visual c++ / MFC** Ordner im linken Bereich. Wählen Sie die **MFC-Klassen aus der Typbibliothek** Symbol aus dem rechten Bereich und auf **öffnen**.

1. In der **Assistenten zum Hinzufügen von Klassen aus der Typbibliothek** Dialogfeld wählen eine Typbibliothek aus der **Verfügbare Typbibliotheken** Dropdown-Liste. Die **Schnittstellen** Feld zeigt die Schnittstellen, die für die ausgewählte Bibliothek verfügbar.

    > [!NOTE]
    >  Sie können Schnittstellen aus mehr als eine Typbibliothek auswählen.

   Wählen Sie die Schnittstellen, darauf doppelklicken, oder klicken Sie auf die **hinzufügen** Schaltfläche. Wenn Sie dies tun, Namen für die Dispatchklassen werden in der **generierte Klassen** Feld. Sie können den Klassennamen in Bearbeiten der `Class` Feld.

   Die **Datei** Feld zeigt die Datei, die in der Klasse deklariert werden. (Sie können diesen sowie den Dateinamen bearbeiten). Sie können auch die Schaltfläche zum Durchsuchen verwenden, wählen Sie andere Dateien, wenn Sie lieber die Header- und Implementierungsdateien Informationen, die in vorhandenen Dateien oder in einem anderen Verzeichnis als dem Projektverzeichnis geschrieben haben.

    > [!NOTE]
    >  Die Dispatchklassen für die ausgewählten Schnittstellen werden in der hier angegebenen Datei platziert. Wenn Sie die Schnittstellen deklariert werden, in verschiedenen Headern möchten, müssen Sie diesen Assistenten für jeden Header-Datei ausführen, die Sie erstellen möchten.

    > [!NOTE]
    >  Einige Informationen in der Typbibliothek kann in Dateien gespeichert werden. -DLL. OCX, oder. Erweiterungen der OLB-Datei.

1. Klicken Sie auf **Fertig stellen**.

   Der Assistent wird dann den Code für die Dispatchklassen, die mit den angegebenen Klassen- und Dateinamen schreiben.

## <a name="see-also"></a>Siehe auch

[Automatisierungsclients](../mfc/automation-clients.md)

