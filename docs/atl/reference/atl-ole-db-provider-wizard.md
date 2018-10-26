---
title: ATL-OLE DB-Anbieter-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.provider.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL OLE DB Provider Wizard
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9710fd4c770f17afb8902b80241179aa20344c1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060728"
---
# <a name="atl-ole-db-provider-wizard"></a>ATL-OLE DB-Anbieter-Assistent

Dieser Assistent erstellt die Klassen, die einen OLE DB-Anbieter zu erstellen.

> [!WARNING]
> Ab Version 15.9 von Visual Studio 2017 ist dieser Codeassistent veraltet. Er wird in einer zukünftigen Version von Visual Studio entfernt. Dieser Assistent wird nur selten verwendet. Die Entfernung dieses Assistenten wirkt sich nicht auf die allgemeine Unterstützung für Active Template Library (ATL) und Microsoft Foundation Classes (MFC) aus. In [dieser Umfrage](https://www.surveymonkey.com/r/QDWKKCN) können Sie Ihr Feedback zu dieser Veraltung mitteilen. Ihr Feedback ist uns wichtig.

## <a name="remarks"></a>Hinweise

Ab Visual Studio 2008 wird von diesem Assistenten erstellte Registrierungsskript seine COM-Komponenten unter registriert **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **registerkomponenten für alle Benutzer** des ATL-Assistenten die Option.

Die folgende Tabelle beschreibt die Optionen für die der ATL-OLE DB-Anbieter-Assistent:

- **Kurzname**

   Geben Sie den kurzen Namen des Anbieters erstellt werden. Die anderen Eingabefelder im Assistenten werden automatisch aufgefüllt. basierend auf Ihrer Eingabe. Sie können die anderen Namensfelder bearbeiten, wenn Sie möchten.

- **Co-Klasse**

   Der Name der Co-Klasse. Die ProgID-Name ändert sich entsprechend diesem Namen.

- **Zugeordnet sind**

   Diese Option gibt an, ob der Assistent mithilfe von Attributen oder Vorlagendeklarationen Anbieterklassen erstellt. Wenn Sie diese Option auswählen, verwendet der Assistent Attribute anstatt von Vorlagendeklarationen (Dies ist die Standardoption, wenn Sie ein attributiertes Projekt erstellt haben). Wenn Sie diese Option deaktivieren, verwendet der Assistent Vorlagendeklarationen anstelle von Attributen (Dies ist die Standardoption, wenn Sie ein nicht attributierten Projekt erstellt haben).

   Wenn Sie diese Option auswählen, wenn Sie ein nicht attributierten Projekt erstellt haben, werden Sie in der Assistenten gewarnt, dass das Projekt in einem attributierten Projekt konvertiert wird und gefragt wird, ob Sie fortfahren.

- **ProgID**

   Die ProgID oder programmgesteuerte Bezeichner, ist die Zeichenfolge, die Ihre Anwendung nicht auf einer GUID verwenden können. Die ProgID-Name weist das Format *Projectname.Coclassname*.

- **Version**

   Die Versionsnummer des Anbieters. Der Standard ist 1.

- **DataSource-Klasse**

   Der Name der Datenquellklasse im C-Format*Shortname*Quelle.

- **DataSource-h-Datei**

   Die Headerdatei für die Datenquellenklasse. Sie können den Dateinamen bearbeiten oder eine vorhanden Headerdatei auswählen.

- **Sitzungsklasse**

   Der Name der Sitzungsklasse des Formulars C*Shortname*Sitzung.

- **Sitzung .h-Datei**

   Die Headerdatei für die Sitzungsklasse. Sie können den Dateinamen bearbeiten oder eine vorhanden Headerdatei auswählen.

- **Command-Klasse**

   Der Name der Befehlsklasse, im Format C*Shortname*Befehl.

- **Befehl .h-Datei**

   Die Headerdatei für die Klasse des Befehls. Dieser Name kann nicht bearbeitet werden und hängt von den Namen der Rowset-Headerdatei.

- **Rowset-Klasse**

   Der Name der Rowset-Klasse des Formulars C*Shortname*Rowset.

- **Rowset-h-Datei**

   Die Headerdatei für die Rowsetklasse. Sie können den Dateinamen bearbeiten oder eine vorhanden Headerdatei auswählen.

- **Rowset-cpp-Datei**

   Der Anbieter Implementierungsdatei einschließen. Sie können den Dateinamen bearbeiten oder eine vorhandene Implementierungsdatei auswählen.

## <a name="see-also"></a>Siehe auch

[ATL-OLE DB-Anbieter](../../atl/reference/adding-an-atl-ole-db-provider.md)

