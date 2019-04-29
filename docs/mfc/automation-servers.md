---
title: Automatisierungsserver
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 39e870db2f5476a630a8ed3bc68944dbb164d469
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374167"
---
# <a name="automation-servers"></a>Automatisierungsserver

Automation ermöglicht es für Ihre Anwendung in einer anderen Anwendung implementierten Objekte zu bearbeiten oder Objekte verfügbar zu machen, damit sie bearbeitet werden können. Ein Automatisierungsserver ist eine Anwendung, die programmierbare Objekte (Automatisierungsobjekte genannt) für andere Anwendungen verfügbar macht (namens [Automatisierungsclients](../mfc/automation-clients.md)). Automatisierungsserver werden manchmal als Automatisierungskomponenten bezeichnet.

Verfügbarmachen von Automation-Objekten ermöglicht Clients, die für bestimmte Vorgänge zu automatisieren, indem Sie direkten Zugriff auf die Objekte und Funktionalität der Server zur Verfügung. Verfügbarmachen von Objekten auf diese Weise ist von Vorteil, wenn Anwendungen Funktionen bereitstellen, die für andere Anwendungen nützlich ist. Beispielsweise kann ein reines Textverarbeitungsprogramm die rechtschreibprüfungsfunktion verfügbar machen, damit anderen Programmen verwendet werden kann. Das Verfügbarmachen von Objekten ermöglicht daher Herstellern, die Funktionalität ihrer Anwendungen zu verbessern, indem Sie die vordefinierten Funktionen von anderen Anwendungen.

Diese Automatisierungsobjekte besitzen Eigenschaften und Methoden als externe Schnittstelle. Der benannte Eigenschaften sind Attribute des Automatisierungsobjekts. Eigenschaften sind z. B. Datenmember einer C++-Klasse. Methoden sind Funktionen, die für Automation-Objekte zusammenarbeiten. Methoden sind wie die öffentlichen Member-Funktionen eine C++-Klasse.

> [!NOTE]
>  Auch Eigenschaften wie die C++-Datenmember sind, sind sie nicht direkt zugegriffen werden kann. Um transparenten Zugriff bereitzustellen, können Sie eine interne Variable im Automation-Objekt mit einem Paar von Memberfunktionen get-/Set richten Sie ein, für den Zugriff darauf.

Durch Verfügbarmachen von Anwendungsfunktionen über eine gemeinsame, klar definierte Schnittstelle, ermöglicht Automation die Erstellung von Anwendungen in einer einzelnen allgemeinen Programmiersprache wie Microsoft Visual Basic nicht in unterschiedlichen, anwendungsspezifische-Makro Sprachen.

##  <a name="_core_support_for_automation_servers"></a> Unterstützung für Automatisierungsserver

Visual C++ und MFC-Framework bieten umfassende Unterstützung für Automatisierungsserver aus. Sie behandeln Großteil des Aufwands beim Durchführen eines Automatisierungsservers, damit Sie Ihre bemühungen auf die Funktionalität Ihrer Anwendung konzentrieren können.

Die Framework principal-Mechanismus für die Unterstützung der Automatisierung ist die Dispatchzuordnung, mit einem Satz von Makros, die in den Deklarationen und Aufrufe erforderlich, um Methoden und Eigenschaften für OLE verfügbar machen erweitert wird. Eine typische Dispatchzuordnung sieht folgendermaßen aus:

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

Das Fenster "Eigenschaften" und Class View unterstützen bei der Verwaltung von Dispatchzuordnungen. Wenn Sie eine neue Methode oder Eigenschaft auf eine Klasse hinzufügen, fügt Visual C++ eine entsprechende `DISP_FUNCTION` oder `DISP_PROPERTY` Makro mit Parametern, der angibt, den Klassennamen, die externen und internen Namen der Methode oder Eigenschaft und Daten.

Die **Klasse hinzufügen** Dialogfeld vereinfacht auch die Deklaration des Automation-Klassen und die Verwaltung von deren Eigenschaften und Operationen. Wenn Sie das Dialogfeld "Klasse hinzufügen" verwenden, um eine Klasse zu Ihrem Projekt hinzuzufügen, geben Sie ihrer Basisklasse. Wenn die Basisklasse Automation zulässt, zeigt das Dialogfeld Klasse hinzufügen Steuerelemente, die Sie verwenden, um die festlegen, ob die neue Klasse Automatisierung unterstützen sollte, ob es "OLE erstellt" (d. h., ob Objekte der Klasse für eine Anforderung von einem COM-Client erstellt werden können) an. , und den externen Namen für die COM-Client verwenden.

Die **Klasse hinzufügen** Dialogfeld erstellt dann eine Klassendeklaration, einschließlich der die entsprechenden Makros für die OLE-features Sie angegeben haben. Darüber hinaus wird das Codegerüst für die Implementierung von Memberfunktionen der Klasse hinzugefügt.

Der MFC-Anwendung-Assistent vereinfacht die Schritte zum Abrufen Ihrer Automation-Server-Anwendung das fliegen. Bei Auswahl von der **Automation** Kontrollkästchen aus der **erweiterte Funktionen** Seite MFS-Anwendungsassistenten fügt der Anwendung das `InitInstance` Funktionsaufrufe erforderlich, um die Automatisierung zu registrieren Objekte und Ihre Anwendung als Automatisierungsserver ausführen.

### <a name="what-do-you-want-to-do"></a>Was möchten Sie tun

- [Erfahren Sie mehr über die Benutzeroberflächenautomatisierungs-clients](../mfc/automation-clients.md)

- [Erfahren Sie mehr über CCmdTarget-Klasse](../mfc/reference/ccmdtarget-class.md)

- [Erfahren Sie mehr über COleDispatchDriver-Klasse](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>Siehe auch

[Automatisierung](../mfc/automation.md)<br/>
[MFC-Anwendungs-Assistent](../mfc/reference/mfc-application-wizard.md)
