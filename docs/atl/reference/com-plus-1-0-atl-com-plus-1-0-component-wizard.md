---
title: COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.mts.options
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
ms.openlocfilehash: 83b7beafe537f6b271b254d16505b515a41acf27
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496689"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent

::: moniker range="vs-2019"

Dieser Assistent ist in Visual Studio 2019 und höher nicht verfügbar.

::: moniker-end

::: moniker range="<=vs-2017"

Verwenden Sie diese Seite des ATL COM+ 1.0-Komponenten-Assistenten, um den Schnittstellentyp und weitere Schnittstellen anzugeben, die unterstützt werden sollen.

Weitere Informationen zu ATL-Projekten und ATL-COM-Klassen finden Sie unter [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md).

- **Interface**

   Gibt den Typ der Schnittstelle an, die vom Objekt unterstützt wird. Standardmäßig unterstützt das Objekt eine duale Schnittstelle.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Dual**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt (seine vtable enthält benutzerdefinierte Funktionen und `IDispatch`-Methoden für späte Bindung). Ermöglicht es sowohl COM-Clients als auch Automation-Controllern, auf das Objekt zuzugreifen.|
   |**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt (seine vtable enthält benutzerdefinierte Schnittstellenfunktionen). Eine benutzerdefinierte Schnittstelle kann schneller sein als eine duale Schnittstelle, insbesondere über Prozessgrenzen hinweg.<br /><br /> - **Automation compatible** Fügt der benutzerdefinierten Schnittstelle Automation-Unterstützung hinzu. Legt für attributierte Projekte das **oleautomation**-Attribut in der Co-Klasse (coclass) fest.|

- **Queueable**

   Gibt an, dass Clients diese Komponente asynchron über Nachrichtenwarteschlangen aufrufen können. Fügt das komponentenattributierte Makro „custom(TLBATTR_QUEUEABLE,0)“ zur .h-Datei (attributierte Projekte) oder zur .idl-Datei (nicht attributierte Projekte) hinzu.

- **Support**

   Gibt zusätzliche Unterstützung für Fehlerbehandlung und Objektsteuerung an.

   |Option|Beschreibung|
   |------------|-----------------|
   |**ISupportErrorInfo**|Erstellt Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)-Schnittstelle, damit das Objekt Fehlerinformationen an den Client zurückgeben kann.|
   |**IObjectControl**|Ermöglicht Ihrem Objekt Zugriff auf die drei [IObjectControl](/windows/win32/api/comsvcs/nn-comsvcs-iobjectcontrol)-Methoden: [Activate](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-activate), [CanBePooled](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled) und [Deactivate](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate).|
   |**IObjectConstruct**|Erstellt Unterstützung für die [IObjectConstruct](/windows/win32/api/comsvcs/nn-comsvcs-iobjectconstruct)-Schnittstelle, um Parameter zu verwalten, die von anderen Methoden oder Objekten übergeben wurden.|

- **Transaktion**

   Gibt an, dass das Objekt Transaktionen unterstützt. Enthält die Datei „mtxattr.h“ und die .idl-Datei (nicht attributierte Projekte).

   |Option|Beschreibung|
   |------------|-----------------|
   |**Unterstützt**|Gibt an, dass das Objekt nie der Ausgangspunkt eines Transaktionsdatenstroms ist, indem das Komponentenattributmakro „custom(TLBATTR_TRANS_SUPPORTED,0)“ zur .h-Datei (attributierte Projekte) oder zur .idl-Datei (nicht attributierte Projekte) hinzugefügt wird.|
   |**Erforderlich**|Gibt an, dass das Objekt der Ausgangspunkt eines Transaktionsdatenstroms sein kann, indem das Komponentenattributmakro „custom(TLBATTR_TRANS_REQUIRED,0)“ zur .h-Datei (attributierte Projekte) oder zur .idl-Datei (nicht attributierte Projekte) hinzugefügt wird.|
   |**Nicht unterstützt**|Gibt an, dass das Objekt Transaktionen ausschließt. Fügt das Komponentenattributmakro „custom(TLBATTR_TRANS_NOTSUPP,0)“ zur .h-Datei (attributierte Projekte) oder zur .idl-Datei (nicht attributierte Projekte) hinzu.|
   |**Requires new**|Gibt an, dass das Objekt immer der Ausgangspunkt eines Transaktionsdatenstroms ist, indem das Komponentenattributmakro „custom(TLBATTR_TRANS_REQNEW,0)“ zur .h-Datei (attributierte Projekte) oder zur .idl-Datei (nicht attributierte Projekte) hinzugefügt wird.|

::: moniker-end

## <a name="see-also"></a>Siehe auch

[ATL COM+ 1.0 Komponenten-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)<br/>
[ATL COM+ 1.0-Komponente](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
