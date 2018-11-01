---
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
- ccustomcommand
- customrs.h
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: a2261d62775c8063d166c664a02fdf3be0d70d17
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651203"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

Die `CCustomCommand` Klasse ist die Implementierung für die Anbieter-Befehlsobjekt. Es stellt die Implementierung für die `IAccessor`, `ICommandText`, und `ICommandProperties` Schnittstellen. Die `IAccessor` Schnittstelle ist identisch mit den im Rowset. Das Befehlsobjekt verwendet die Zugriffsmethode, um Bindungen für Parameter anzugeben. Das Rowsetobjekt, das verwendet werden, um Bindungen für Ausgabespalten anzugeben. Die `ICommandText` Schnittstelle ist eine gute Möglichkeit, einen Textbefehl anzugeben. Dieses Beispiel verwendet die `ICommandText` Schnittstelle später noch Mal, wenn sie benutzerdefinierten Code hinzufügt; Außerdem überschreibt er die `ICommand::Execute` Methode. Die `ICommandProperties` Schnittstelle verarbeitet alle Eigenschaften für die Befehls- und Rowsetobjekte-Objekte.

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

Die `IAccessor` Schnittstelle verwaltet alle Bindungen in Befehle und Rowsets verwendet. Der Consumer ruft `IAccessor::CreateAccessor` mit einem Array von `DBBINDING` Strukturen. Jede `DBBINDING` Struktur enthält die Informationen darüber, wie die spaltenbindungen (z. B. Typ und Länge) behandelt werden sollen. Der Anbieter empfängt die Strukturen und bestimmt dann, wie die Daten übertragen werden sollen, und gibt an, ob eine Konvertierung erforderlich sind. Die `IAccessor` Schnittstelle wird im Befehlsobjekt verwendet, um alle Parameter im Befehl zu verarbeiten.

Das Command-Objekt enthält auch eine Implementierung des `IColumnsInfo`. OLE DB erfordert die `IColumnsInfo` Schnittstelle. Die Schnittstelle ermöglicht es, Informationen zu Parametern des Befehls abrufen. Verwendet das Rowsetobjekt, das die `IColumnsInfo` -Schnittstelle zur Rückgabe von Informationen zu den Ausgabespalten an den Anbieter.

Der Anbieter enthält auch eine Schnittstelle namens `IObjectWithSite`. Die `IObjectWithSite` Schnittstelle wurde in ATL 2.0 implementiert, und ermöglicht der Implementierung, die Informationen über sich selbst zu ihrem untergeordneten Element übergeben. Das Befehlsobjekt verwendet die `IObjectWithSite` generiert anzuweisen, eine Rowset-Objekte, die sie erstellt wurden.

## <a name="see-also"></a>Siehe auch

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)