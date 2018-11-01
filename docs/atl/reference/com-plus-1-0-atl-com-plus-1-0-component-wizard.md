---
title: COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.mts.options
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
ms.openlocfilehash: 014193f4017aa47b819558cbd4753e6abcffcaaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562057"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent

Verwenden Sie auf dieser Seite des ATL COM+ 1.0 Komponenten-Assistenten, geben Sie den Schnittstellentyp und weitere Schnittstellen unterstützt werden.

Weitere Informationen zu ATL-Projekte und ATL-COM-Klassen finden Sie unter [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).

- **Interface**

   Gibt den Typ der Schnittstelle, die das Objekt unterstützt. Das Objekt unterstützt standardmäßig eine duale Schnittstelle.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Dual**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt (die Vtable besitzt, benutzerdefinierte Funktionen und späte Bindung `IDispatch` Methoden). Ermöglicht es COM-Clients sowohl Automatisierungscontroller auf das Objekt zuzugreifen.|
   |**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt (die Vtable hat benutzerdefinierte Funktionen). Eine benutzerdefinierte Schnittstelle kann vor allem über Prozessgrenzen hinweg schneller als das duale Schnittstelle sein.<br /><br /> - **Automatisierungskompatibel** die benutzerdefinierte Schnittstelle-Unterstützung hinzugefügt. Legt für die attributierte Projekte die **Oleautomation** -Attribut in der Co-Klasse.|

- **Queueable**

   Gibt an, dass Clients auf diese Komponente, die mithilfe von Nachrichtenwarteschlangen asynchron aufrufen können. Fügt die Komponente, die attributiert Custom (TLBATTR_QUEUEABLE-Komponentenattributmakro, 0) der h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte) hinzu.

- **Unterstützung**

   Gibt zusätzliche Unterstützung für die Behandlung und Objekt-Steuerelement für Fehlermeldungen an.

   |Option|Beschreibung|
   |------------|-----------------|
   |**ISupportErrorInfo**|Stellt die Unterstützung der [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) Schnittstelle, damit das Objekt Fehlerinformationen an den Client zurückgeben kann.|
   |**IObjectControl**|Ermöglicht dem Objektzugriff auf die drei [IObjectControl](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectcontrol) Methoden: [aktivieren](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-activate), [CanBePooled](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled), und [deaktivieren](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate).|
   |**IObjectConstruct**|Stellt die Unterstützung der [IObjectConstruct](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectconstruct) Schnittstelle zum Verwalten von in-Parameter von anderen Methoden oder Objekten übergeben.|

- **Transaktion**

   Gibt an, dass das Objekt Transaktionen unterstützt. Die mtxattr.h Datei IDL-Datei (nicht attributierte Projekte).

   |Option|Beschreibung|
   |------------|-----------------|
   |**Unterstützt**|Gibt an, dass das Objekt nie den Stamm eines Streams für die Transaktion durch das Hinzufügen von der Komponente Attribut Makro custom(TLBATTR_TRANS_SUPPORTED,0) der h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).|
   |**Erforderlich**|Gibt an, dass das Objekt kann möglicherweise nicht den Stamm eines Streams für die Transaktion durch das Hinzufügen von der Komponente Attribut Makro custom(TLBATTR_TRANS_REQUIRED,0) der h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).|
   |**Nicht unterstützt**|Gibt an, dass das Objekt Transaktionen ausschließt. Fügt der Custom(TLBATTR_TRANS_NOTSUPP,0)-Komponentenattributmakro der h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte) hinzu.|
   |**Neue erfordert**|Gibt an, dass das Objekt immer den Stamm eines Streams für die Transaktion durch das Hinzufügen von der Komponente Attribut Makro custom(TLBATTR_TRANS_REQNEW,0) der h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).|

## <a name="see-also"></a>Siehe auch

[ATL COM+ 1.0 Komponenten-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)<br/>
[ATL COM+ 1.0-Komponente](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

