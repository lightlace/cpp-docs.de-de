---
title: ATL-COM-Eigenschaftenseiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0da9a0299679ec140888e9536329f0957a786279
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760002"
---
# <a name="atl-com-property-pages"></a>ATL COM-Eigenschaftenseiten

Com-Eigenschaftenseiten bieten eine Benutzeroberfläche zum Festlegen der Eigenschaften (oder Aufrufen der Methoden) von ein oder mehrere COM-Objekten. Eigenschaftenseiten werden häufig von ActiveX-Steuerelementen verwendet, für die Bereitstellung umfassender Benutzeroberflächen, mit die Eigenschaften des Steuerelements zur Entwurfszeit festgelegt werden können.

Eigenschaftenseiten sind COM-Objekte, implementieren die [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) oder [IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) Schnittstelle. Diese Schnittstellen bieten Methoden, mit denen die Seite zugeordnet werden können. eine `site` (ein COM-Objekt, das den Container der Seite darstellt) und eine Reihe von *Objekte* (COM-Objekte, deren Methoden, als Reaktion auf Änderungen aufgerufen werden, vom Benutzer vorgenommene der Eigenschaftenseite auf). Die Seite Eigenschaftencontainer ist verantwortlich für das Aufrufen von Methoden für die Schnittstelle der Eigenschaftenseite auf die Seite informiert, wenn es sich bei ein- oder Ausblenden der Benutzeroberfläche und beim Anwenden die Änderungen durch den Benutzer an der zugrunde liegenden Objekten vorgenommen.

Jede Eigenschaftenseite kann vollständig unabhängig von der Objekte erstellt werden, dessen Eigenschaften festgelegt werden können. Alles ist auf einer Eigenschaftenseite muss zu einer bestimmten Schnittstelle (oder eine Gruppe von Schnittstellen) und eine Benutzeroberfläche bereitstellen, für das Aufrufen von Methoden in dieser Schnittstelle.

Weitere Informationen finden Sie unter [Eigenschaftenblätter und Eigenschaftenseiten](/windows/desktop/com/property-sheets-and-property-pages) im Windows SDK.

## <a name="in-this-section"></a>In diesem Abschnitt

[Festlegen der Eigenschaftenseiten](../atl/specifying-property-pages.md)  
Listet die Schritte zum Festlegen der Eigenschaftenseiten für ein Steuerelement, und zeigt eine Beispielklasse.

[Implementieren der Eigenschaftenseiten](../atl/implementing-property-pages.md)  
Listet die Schritte zum Implementieren der Eigenschaftenseiten, einschließlich Methoden zum Überschreiben. Führt Sie durch ein vollständiges Beispiel für das Beispielprogramm ATLPages Grundlage.

## <a name="related-sections"></a>Verwandte Abschnitte

[ATLPages-Beispiel](../visual-cpp-samples.md)  
Der Beispiel-Zusammenfassung für das ATLPages-Beispiel implementiert eine Eigenschaft mit `IPropertyPageImpl`.

[ATL](../atl/active-template-library-atl-concepts.md)  
Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)

