---
title: Formularansichten (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
ms.openlocfilehash: d5bb61aaad767b1322c12f57ec16ae59cb75148c
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331541"
---
# <a name="form-views-mfc"></a>Formularansichten (MFC)

Sie können alle Visual C++-Anwendung mit Unterstützung für die MFC-Bibliotheken, einschließlich Formen Hinzufügen einer [Forms basierende Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md) (eine, deren View-Klasse abgeleitet ist `CFormView`). Wenn Sie Ihre Anwendung zur Unterstützung von Formularen anfänglich nicht erstellt haben, wird Visual C++ diese Unterstützung für die Sie hinzufügen, wenn Sie ein neues Formular einfügen. In einer SDI- oder MDI-Anwendung, die dem implementiert die Standardseite [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md), wenn der Benutzer wählt die **neu** Befehl (standardmäßig auf die **Datei** Menü), Visual C++ wird der Benutzer zur Auswahl der verfügbaren Formulare aufgefordert.

Mit einer SDI-Anwendung, wenn der Benutzer wählt die **neu** Befehl die aktuelle Instanz des Formulars wird weiterhin ausgeführt, aber eine neue Instanz der Anwendung mit das ausgewählte Formular wird erstellt, wenn keiner gefunden wird. In einer MDI-Anwendung, die aktuelle Instanz des Formulars ausgeführt, wenn der Benutzer weiterhin die **neu** Befehl.

> [!NOTE]
>  Sie können ein Formular in eine auf Dialogfeldern basierende Anwendung einfügen (, deren Dialogfeldklasse basiert auf, einer `CDialog` und eine Klasse wird in der Ansicht nicht implementiert). Allerdings ohne die Dokument-/Ansichtarchitektur, Visual C++ automatisch implementiert nicht die **Datei**&#124;**neu** Funktionalität. Sie müssen eine Möglichkeit für den Benutzer an zusätzliche Formulare, z. B. durch die Implementierung ein Dialogfeld im Registerformat mit verschiedenen Eigenschaftenseiten erstellen.

Wenn Sie ein neues Formular in Ihre Anwendung einfügen, führt Visual C++ Folgendes aus:

- Erstellt eine Klasse, die basierend auf einer der Formular-Stil-Klassen, die Sie auswählen (`CFormView`, `CRecordView`, `CDaoRecordView`, oder `CDialog`).

- Erstellt eine Dialogfeldressource mit der entsprechenden Stile (oder Sie können eine vorhandenen Dialog-Ressource, die noch nicht zu einer Klasse wurde).

   Wenn Sie eine vorhandenen Dialog-Ressource auswählen, müssen Sie diese Stile festgelegt werden, mithilfe der Seite "Eigenschaften" für das Dialogfeld. Formate für ein Dialogfeld müssen Folgendes enthalten:

     **WS_CHILD**= On

     **WS_BORDER**= Off

     **WS_VISIBLE**= Off

     **WS_CAPTION**= Off

Für Anwendungen, die basierend auf der Dokument-/Ansichtarchitektur die **Formulars** Befehl (Rechtsklick in der Klassenansicht) auch:

- Erstellt eine `CDocument`-basierten Klasse

   Anstatt eine neue Klasse erstellt haben, können Sie alle vorhandenen `CDocument`-basierten Klasse im Projekt.

- Generiert eine Dokumentvorlage (abgeleitet `CDocument`) mit der Zeichenfolge, Menüs und Symbol für Ressourcen.

   Sie können auch auf der Basis der Vorlage für eine neue Klasse erstellen.

- Fügt einen Aufruf von `AddDocumentTemplate` in Ihrer Anwendungsverzeichnis `InitInstance` Code.

   Fügt dieser Code für jedes neue Formular erstellen, die Liste der verfügbaren Formulare des Formulars hinzugefügt, wenn der Benutzer auswählt Visual C++ die **neu** Befehl. Dieser Code umfasst verknüpfte Ressourcen-ID des Formulars und die Namen der der zugeordnete Dokument anzeigen und Frameklassen, aus denen die neue Form-Objekt besteht.

   Dokumentvorlagen dienen als Verbindung zwischen Dokumenten, Rahmenfenstern und Ansichten. Für ein einzelnes Dokument können Sie viele Vorlagen erstellen.

Weitere Informationen finden Sie unter:

- [Erstellen einer formularbasierten Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Einfügen eines Formulars in ein Projekt](../mfc/inserting-a-form-into-a-project.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
