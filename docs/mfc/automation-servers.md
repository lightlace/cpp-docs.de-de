---
title: Automatisierungsserver
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 510acfa032ca4303962164a19130ecd1971060fc
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907962"
---
# <a name="automation-servers"></a>Automatisierungsserver

Automation ermöglicht es Ihrer Anwendung, in einer anderen Anwendung implementierte Objekte zu bearbeiten oder Objekte verfügbar zu machen, damit Sie bearbeitet werden können. Ein Automatisierungsserver ist eine Anwendung, die programmierbare Objekte (sogenannte Automatisierungs Objekte) für andere Anwendungen ( [Automatisierungs Clients](../mfc/automation-clients.md)genannt) verfügbar macht. Automatisierungsserver werden manchmal auch als Automatisierungskomponenten bezeichnet.

Durch das verfügbar machen von Automatisierungs Objekten können Clients bestimmte Verfahren automatisieren, indem Sie direkt auf die Objekte und Funktionen zugreifen, die der Server zur Verfügung stellt Das verfügbar machen von Objekten auf diese Weise ist vorteilhaft, wenn Anwendungen Funktionen bereitstellen, die für andere Anwendungen nützlich sind. Beispielsweise kann ein Textverarbeitungsprogramm seine Funktion zur Rechtschreibprüfung verfügbar machen, sodass es von anderen Programmen verwendet werden kann. Das verfügbar machen von Objekten ermöglicht es den Anbietern, die Funktionalität Ihrer Anwendungen mithilfe der vorgefertigten Funktionen anderer Anwendungen zu verbessern.

Diese Automatisierungs Objekte verfügen über Eigenschaften und Methoden als externe Schnittstelle. Eigenschaften sind benannte Attribute des Automatisierungs Objekts. Eigenschaften entsprechen den Datenmembern einer C++ Klasse. Methoden sind Funktionen, die an Automatisierungs Objekten arbeiten. Methoden sind wie die öffentlichen Member-Funktionen einer C++ -Klasse.

> [!NOTE]
>  Obwohl Eigenschaften wie C++ Datenmember sind, kann auf Sie nicht direkt zugegriffen werden. Um transparenten Zugriff zu ermöglichen, richten Sie eine interne Variable im Automation-Objekt mit einem Paar von Get/Set-Element Funktionen ein, um darauf zuzugreifen.

Durch die Bereitstellung von Anwendungsfunktionen über eine gemeinsame, klar definierte Schnittstelle ermöglicht Automation die Erstellung von Anwendungen in einer einzelnen allgemeinen Programmiersprache, wie z. b. Microsoft Visual Basic, anstatt in einem unterschiedlichen, anwendungsspezifischen Makro. Sprachen.

##  <a name="_core_support_for_automation_servers"></a>Unterstützung für Automatisierungsserver

Visual C++ und das MFC-Framework bieten umfassende Unterstützung für Automatisierungsserver. Sie bewältigen einen Großteil des Aufwands bei der Erstellung eines Automatisierungs Servers, sodass Sie sich auf die Funktionalität Ihrer Anwendung konzentrieren können.

Der Prinzipal Mechanismus des Frameworks für die Unterstützung von Automation ist die Dispatchzuordnung, eine Reihe von Makros, die in die Deklarationen und Aufrufe erweitert werden, die erforderlich sind, um Methoden und Eigenschaften für OLE Eine typische dispatchkarte sieht wie folgt aus:

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

Der [Klassen-Assistent](reference/mfc-class-wizard.md) und Klassenansicht unterstützen die Verwaltung von dispatchmaps. Wenn Sie einer Klasse eine neue Methode oder Eigenschaft hinzufügen, fügt Visual Studio ein entsprechendes `DISP_FUNCTION` - `DISP_PROPERTY` oder-Makro mit Parametern hinzu, die den Klassennamen, die externen und internen Namen der Methode oder Eigenschaft sowie die Datentypen angeben.

Das Dialogfeld **Klasse hinzufügen** vereinfacht auch die Deklaration von Automatisierungs Klassen und die Verwaltung ihrer Eigenschaften und Vorgänge. Wenn Sie das Dialogfeld Klasse hinzufügen verwenden, um dem Projekt eine Klasse hinzuzufügen, geben Sie die zugehörige Basisklasse an. Wenn die Basisklasse Automation zulässt, werden im Dialogfeld Klasse hinzufügen Steuerelemente angezeigt, mit denen Sie angeben können, ob die neue Klasse Automation unterstützen soll, ob Sie "OLE-erstellbar" ist (d. h. ob Objekte der Klasse für eine Anforderung von einem com-Client erstellt werden können). und der externe Name, den der com-Client verwenden soll.

Im Dialogfeld **Klasse hinzufügen** wird dann eine Klassen Deklaration erstellt, einschließlich der entsprechenden Makros für die OLE-Funktionen, die Sie angegeben haben. Außerdem wird der Skeleton-Code für die Implementierung der Member-Funktionen Ihrer Klasse hinzugefügt.

Der MFC-Anwendungs-Assistent vereinfacht die Schritte, die erforderlich sind, um Ihre Automation Server-Anwendung zu beenden. Wenn Sie auf der Seite **Erweiterte Features** das Kontrollkästchen `InitInstance` **Automatisierung** aktivieren, fügt der MFC-Anwendungs-Assistent der Funktion der Anwendung die erforderlichen Aufrufe zum Registrieren Ihrer Automation-Objekte und zum Ausführen der Anwendung als Automation-Server.

### <a name="what-do-you-want-to-do"></a>Was möchten Sie tun?

- [Weitere Informationen zu Automatisierungs Clients](../mfc/automation-clients.md)

- [Weitere Informationen über die Klasse CCmdTarget](../mfc/reference/ccmdtarget-class.md)

- [Weitere Informationen zur Klasse COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>Siehe auch

[Automatisierung](../mfc/automation.md)<br/>
[MFC-Anwendungs-Assistent](../mfc/reference/mfc-application-wizard.md)
