---
title: Benutzeroberflächenautomatisierungs-Clients | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdc9b47bbd7b639850a13a77b81ef4802a301ba7
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890061"
---
# <a name="automation-clients"></a>Automatisierungsclients

Automation ermöglicht es für Ihre Anwendung in einer anderen Anwendung implementierten Objekte zu bearbeiten oder Objekte verfügbar zu machen, damit sie bearbeitet werden können. Ein Automatisierungsclient ist eine Anwendung, die verfügbar gemachten Objekten gehören zu einer anderen Anwendung bearbeiten können. Die Anwendung, die die Objekte verfügbar macht, wird den Automation-Server aufgerufen. Der Client bearbeitet die Serveranwendung Objekte durch den Zugriff auf diese Objekte Eigenschaften und Funktionen.

### <a name="types-of-automation-clients"></a>Typen von Benutzeroberflächenautomatisierungs-Clients

Es gibt zwei Arten von Benutzeroberflächenautomatisierungs-Clients:

- Clients, die dynamisch (zur Laufzeit) Informationen zu den Eigenschaften und Vorgänge des Servers abrufen.

- Clients, die statischen Informationen (zum Zeitpunkt der Kompilierung) verfügen, die die Eigenschaften und Vorgänge des Servers angibt.

Clients für die erste Art Abrufen von Informationen zu Methoden und Eigenschaften des Servers durch Abfragen der OLE-System `IDispatch` Mechanismus. Obwohl es ausreichend, um verwenden Sie für dynamische Clients ist `IDispatch` ist schwierig, die für statische Clients zu verwenden, kompilieren Sie die Objekte, die derzeit zum bekannt sein muss, in denen Zeit. Geben Sie der Microsoft Foundation Classes für statische Clients gebunden, die [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) Klasse.

Statisch gebundene Clients verwenden eine Proxyklasse, die statisch verknüpft ist, mit der Clientanwendung. Diese Klasse stellt eine typsichere C++-Kapselung von Eigenschaften und Operationen der Serveranwendung.

Die Klasse `COleDispatchDriver` bietet die Dienstprinzipale-Unterstützung für die Clientseite der Automatisierung. Mithilfe der **neues Element hinzufügen** Dialogfeld erstellen Sie eine Klasse, die von abgeleiteten `COleDispatchDriver`.

Anschließend geben Sie die Typbibliothek-Datei, die die Eigenschaften und Funktionen der Serveranwendung Objekts beschreibt. Das Dialogfeld "Element hinzufügen" liest diese Datei und erstellt die `COleDispatchDriver`-abgeleitete Klasse sein, mit Memberfunktionen, die Ihre Anwendung aufrufen können, die Server-Anwendung Zugriff auf Objekte in C++ in einer typsicheren Weise. Zusätzliche Funktionen, die von geerbten `COleDispatchDriver` vereinfacht das Aufrufen des entsprechenden Automatisierungsservers.

### <a name="handling-events-in-automation-clients"></a>Behandeln von Ereignissen in Benutzeroberflächenautomatisierungs-Clients

Sie können zum Behandeln von Ereignissen in Ihrem Automatisierungsclient müssen Sie eine Senkenschnittstelle hinzufügen. MFC enthält assistentenunterstützung senkenschnittstellen für ActiveX-Steuerelemente hinzufügen, jedoch nicht für andere COM_Server unterstützt.

## <a name="see-also"></a>Siehe auch

[Automatisierungsclients: Verwenden von Typbibliotheken](../mfc/automation-clients-using-type-libraries.md)<br/>
[Automatisierung](../mfc/automation.md)<br/>
[MFC-Anwendungs-Assistent](../mfc/reference/mfc-application-wizard.md)

