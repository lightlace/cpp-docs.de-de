---
title: ATL-OLE DB-Anbieter-Assistent
ms.date: 05/09/2019
helpviewer_keywords:
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
ms.openlocfilehash: 91384d6c61368ee56ed303622e5c1bdfad09bd8a
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65706962"
---
# <a name="atl-ole-db-provider-wizard"></a>ATL-OLE DB-Anbieter-Assistent

::: moniker range="vs-2019"

Dieser Assistent ist in Visual Studio 2019 und höher nicht verfügbar.

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="remarks"></a>Anmerkungen

Ab Visual Studio 2008 werden mit dem von diesem Assistenten generierten Registrierungsskript die zugehörigen COM-Komponenten nicht unter **HKEY_LOCAL_MACHINE**, sondern unter **HKEY_CURRENT_USER** registriert. Um dieses Verhalten zu ändern, legen Sie die Option **Komponente für alle Benutzer registrieren** des ATL-Assistenten fest.

Die folgende Tabelle beschreibt die Optionen für den ATL-OLE DB-Anbieter-Assistenten:

- **Kurzname**

   Geben Sie den Kurznamen des Anbieters ein, der erstellt werden soll. Die weiteren Bearbeitungsfelder im Assistenten werden basierend auf Ihrer hier vorgenommenen Eingabe automatisch aufgefüllt. Sie können bei Bedarf die weiteren Namensfelder bearbeiten.

- **Co-Klasse**

   Der Name der Co-Klasse. Der ProgID-Name wird geändert, um diesem Namen zu entsprechen.

- **Attributiert**

   Diese Option gibt an, ob der Assistent Anbieterklassen mithilfe von Attributen oder Vorlagendeklarationen erstellt. Bei Auswahl dieser Option verwendet der Assistent Attribute anstelle von Vorlagendeklarationen (dies ist die Standardoption, wenn Sie ein attributiertes Objekt erstellen). Wenn Sie diese Option deaktivieren, verwendet der Assistent Vorlagendeklarationen anstelle von Attribute (dies ist die Standardoption, wenn Sie ein nicht attributiertes Projekt erstellen).

   Wenn Sie diese Option bei Erstellung eines nicht attributierten Projekts aktivieren, werden Sie vom Assistenten gewarnt, dass das Projekt in ein attributiertes Projekt konvertiert wird, und Sie können entscheiden, ob Sie den Vorgang fortsetzen möchten oder nicht.

- **ProgID**

   Dieser programmgesteuerte Bezeichner ist eine Textzeichenfolge, den Ihre Anwendung anstelle einer GUID verwenden kann. Der ProgID-Name hat die Form *NameProjekt.NameCo-Klasse*.

- **Version**

   Die Versionsnummer Ihres Anbieters. Der Standard ist 1.

- **DataSource-Klasse**

   Der Name der Datenquellenklasse in der Form C*Kurzname*Source.

- **DataSource-H-Datei**

   Die Headerdatei für die Datenquellenklasse. Sie können den Namen dieser Datei bearbeiten oder eine vorhandene Headerdatei auswählen.

- **Sitzungsklasse**

   Der Name der Sitzungsklasse in der Form C*Kurzname*Session.

- **Sitzungs-H-Datei**

   Die Headerdatei für die Sitzungsklasse. Sie können den Namen dieser Datei bearbeiten oder eine vorhandene Headerdatei auswählen.

- **Befehlsklasse**

   Der Name der Befehlsklasse in der Form C*Kurzname*Command.

- **Befehls-H-Datei**

   Die Headerdatei für die Befehlsklasse. Der Name kann nicht bearbeitet werden und ist abhängig vom Namen der Headerdatei für das Rowset.

- **Rowsetklasse**

   Der Name der Rowsetklasse von in der Form C*Kurzname*Rowset.

- **Rowset-H-Datei**

   Die Headerdatei für die Rowsetklasse. Sie können den Namen dieser Datei bearbeiten oder eine vorhandene Headerdatei auswählen.

- **Rowset-CPP-Datei**

   Die Implementierungsdatei des Anbieters. Sie können den Namen dieser Datei bearbeiten oder eine vorhandene Implementierungsdatei auswählen.

::: moniker-end

## <a name="see-also"></a>Siehe auch

[ATL-OLE DB-Anbieter](../../atl/reference/adding-an-atl-ole-db-provider.md)
