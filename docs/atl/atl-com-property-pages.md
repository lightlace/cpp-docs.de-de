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
ms.openlocfilehash: f6f549388e69e9549c64645de758d92822205fd5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491860"
---
# <a name="atl-com-property-pages"></a>ATL COM-Eigenschaftenseiten

COM-Eigenschaften Seiten stellen eine Benutzeroberfläche zum Festlegen der Eigenschaften (oder des Aufrufs der Methoden) von einem oder mehreren COM-Objekten bereit. Eigenschaften Seiten werden häufig von ActiveX-Steuerelementen für die Bereitstellung umfassender Benutzeroberflächen verwendet, mit denen Steuerelement Eigenschaften zur Entwurfszeit festgelegt werden können.

Eigenschaften Seiten sind COM-Objekte, die die [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) -oder [IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) -Schnittstelle implementieren. Diese Schnittstellen stellen Methoden bereit, die es ermöglichen, dass die `site` Seite einem (einem COM-Objekt, das den Container der Seite darstellt) und einer Anzahl von *Objekten* (COM-Objekte, deren Methoden aufgerufen werden, als Reaktion auf Änderungen durch den Benutzer des Eigenschaften Seite). Der Container für die Eigenschaften Seite ist für das Aufrufen von Methoden auf der Eigenschaften Seiten Schnittstelle zuständig, um der Seite mitzuteilen, wann die Benutzeroberfläche angezeigt oder ausgeblendet werden soll und wann die vom Benutzer vorgenommenen Änderungen auf die zugrunde liegenden Objekte angewendet werden sollen.

Jede Eigenschaften Seite kann vollständig unabhängig von den Objekten erstellt werden, deren Eigenschaften festgelegt werden können. Eine Eigenschaften Seite muss lediglich eine bestimmte Schnittstelle (oder einen Satz von Schnittstellen) verstehen und eine Benutzeroberfläche zum Aufrufen von Methoden für diese Schnittstelle bereitstellen.

Weitere Informationen finden Sie unter [Eigenschaften Blätter und Eigenschaften Seiten](/windows/win32/com/property-sheets-and-property-pages) im Windows SDK.

## <a name="in-this-section"></a>In diesem Abschnitt

[Festlegen der Eigenschaftenseiten](../atl/specifying-property-pages.md)<br/>
Listet die Schritte zum Angeben von Eigenschaften Seiten für die Steuerung auf und zeigt eine Beispiel Klasse an.

[Implementieren der Eigenschaftenseiten](../atl/implementing-property-pages.md)<br/>
Listet die Schritte zum Implementieren von Eigenschaften Seiten, einschließlich Methoden zum überschreiben. Führt Sie durch ein umfassendes Beispiel, das auf dem ATLPages-Beispielprogramm basiert.

## <a name="related-sections"></a>Verwandte Abschnitte

[ATLPages-Beispiel](../overview/visual-cpp-samples.md)<br/>
Das Beispiel Abstract für das ATLPages-Beispiel, das eine Eigenschaften Seite mithilfe `IPropertyPageImpl`von implementiert.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)
