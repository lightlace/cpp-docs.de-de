---
title: ATL COM-Eigenschaftenseiten
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
ms.openlocfilehash: 5bc17bfc415576d50c84e880bef955e49d926c86
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595558"
---
# <a name="atl-com-property-pages"></a>ATL COM-Eigenschaftenseiten

Com-Eigenschaftenseiten bieten eine Benutzeroberfläche zum Festlegen der Eigenschaften (oder Aufrufen der Methoden) von ein oder mehrere COM-Objekten. Eigenschaftenseiten werden häufig von ActiveX-Steuerelementen verwendet, für die Bereitstellung umfassender Benutzeroberflächen, mit die Eigenschaften des Steuerelements zur Entwurfszeit festgelegt werden können.

Eigenschaftenseiten sind COM-Objekte, implementieren die [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) oder [IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) Schnittstelle. Diese Schnittstellen bieten Methoden, mit denen die Seite zugeordnet werden können. eine `site` (ein COM-Objekt, das den Container der Seite darstellt) und eine Reihe von *Objekte* (COM-Objekte, deren Methoden, als Reaktion auf Änderungen aufgerufen werden, vom Benutzer vorgenommene der Eigenschaftenseite auf). Die Seite Eigenschaftencontainer ist verantwortlich für das Aufrufen von Methoden für die Schnittstelle der Eigenschaftenseite auf die Seite informiert, wenn es sich bei ein- oder Ausblenden der Benutzeroberfläche und beim Anwenden die Änderungen durch den Benutzer an der zugrunde liegenden Objekten vorgenommen.

Jede Eigenschaftenseite kann vollständig unabhängig von der Objekte erstellt werden, dessen Eigenschaften festgelegt werden können. Alles ist auf einer Eigenschaftenseite muss zu einer bestimmten Schnittstelle (oder eine Gruppe von Schnittstellen) und eine Benutzeroberfläche bereitstellen, für das Aufrufen von Methoden in dieser Schnittstelle.

Weitere Informationen finden Sie unter [Eigenschaftenblätter und Eigenschaftenseiten](/windows/desktop/com/property-sheets-and-property-pages) im Windows SDK.

## <a name="in-this-section"></a>In diesem Abschnitt

[Festlegen der Eigenschaftenseiten](../atl/specifying-property-pages.md)<br/>
Listet die Schritte zum Festlegen der Eigenschaftenseiten für ein Steuerelement, und zeigt eine Beispielklasse.

[Implementieren der Eigenschaftenseiten](../atl/implementing-property-pages.md)<br/>
Listet die Schritte zum Implementieren der Eigenschaftenseiten, einschließlich Methoden zum Überschreiben. Führt Sie durch ein vollständiges Beispiel für das Beispielprogramm ATLPages Grundlage.

## <a name="related-sections"></a>Verwandte Abschnitte

[ATLPages-Beispiel](../visual-cpp-samples.md)<br/>
Der Beispiel-Zusammenfassung für das ATLPages-Beispiel implementiert eine Eigenschaft mit `IPropertyPageImpl`.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)

