---
title: Verbunddokumentunterstützung, MFC-Anwendungs-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.compdoc
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
ms.openlocfilehash: b2ff4f312132b690223f124fd8790d0e2c172b7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373439"
---
# <a name="compound-document-support-mfc-application-wizard"></a>Verbunddokumentunterstützung, MFC-Anwendungs-Assistent

Geben Sie auf dieser Seite des Assistenten für MFC-Anwendung an, zu welchem Grad Ihrer Anwendung zusammengesetzten und active Document-Unterstützung bereitgestellt. Ihre Anwendung muss die Dokument-/Ansichtarchitektur zur Unterstützung von zusammengesetzten Dokumenten und Dokumentvorlagen unterstützen.

Standardmäßig enthält die Anwendung keine Unterstützung für Verbunddokumente benötigt. Wenn Sie diese Standardeinstellung akzeptieren, kann nicht für Ihre Anwendung die aktive Dokumente oder compound-Dateien unterstützen.

- **Unterstützung für Verbunddokumente**

  Bestimmt, ob Ihre Anwendung, Container-Unterstützung, Unterstützung für Server oder beides bereitstellt. Weitere Informationen zu diesem Bereich finden Sie unter:

  - [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md)

  - [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md)

  |Option|Beschreibung|
  |------------|-----------------|
  |**Keine**|Gibt keine Unterstützung für Object Linking and Embedding (OLE). Der Anwendungs-Assistent erstellt standardmäßig eine Anwendung ohne ActiveX-Unterstützung.|
  |**Container**|Enthält verknüpfte und eingebettete Objekte.|
  |**Miniserver**|Gibt an, die Anwendung erstellen und Verwalten von Verbunddokumentobjekte. Beachten Sie, die Mini-Server nicht ausgeführt werden können eigenständig und unterstützt nur eingebettete Elemente.|
  |**Vollserver**|Gibt an, die Anwendung erstellen und Verwalten von Verbunddokumentobjekte. Vollständige Servern werden können eigenständige und unterstützen sowohl verknüpfte eingebettete Elemente ausgeführt.|
  |**Container/Vollserver**|Gibt an, dass die Anwendung sowohl einen Container und einem Server kann. Ein Container ist eine Anwendung, die eingebettete oder verknüpfte Elemente in ihre eigenen Dokumente integrieren kann. Ein Server ist eine Anwendung, die Automation-Elemente für die Verwendung von containeranwendungen erstellen können.|

- **Zusätzliche Optionen**

  Gibt an, ob Ihre Anwendung aktive Dokumente unterstützt. Finden Sie unter [aktive Dokumente](../../mfc/active-documents.md) für Weitere Informationen zu diesem Feature.

  |Option|Beschreibung|
  |------------|-----------------|
  |**Active Document-server**|Gibt an, die Anwendung erstellen und verwalten aktive Dokumente. Wenn Sie diese Option auswählen, müssen Sie eine Dateierweiterung angeben, für den Server für aktive Dokument in der **Dateierweiterung** im Feld der [Zeichenfolgen für Dokumentvorlagen](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Seite des Assistenten. Finden Sie unter [Active Document-Server](../../mfc/active-document-servers.md) für Weitere Informationen.|
  |**Active Document-container**|Gibt an, dass die Anwendung aktiv Dokumente innerhalb des Rahmens enthalten kann. Aktive Dokumente können, z. B. Internet Explorer oder, Office-Dokumenten, z. B. Microsoft Word-Dateien oder Excel-Tabellen enthalten. Finden Sie unter [Active Document-Container](../../mfc/active-document-containment.md) für Weitere Informationen.|
  |**Unterstützung für Verbunddateien**|Die Container-Anwendung-Dokumente, die das zusammengesetzte-Dateiformat wird nicht serialisiert werden. Diese Option erzwingt das Laden von einer vollständigen Datei, die Objekte in den Arbeitsspeicher enthält. Inkrementelle speichert zu individuellen Objekten sind nicht verfügbar. Ein Objekt wurde geändert und anschließend gespeichert, werden dann alle Objekte in der Datei gespeichert.|

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)
