---
title: ATL COM-Eigenschaftenseiten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: de062b5c9aedb064206dfc40f7c722a298ded774
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="atl-com-property-pages"></a>ATL COM-Eigenschaftenseiten
COM-Eigenschaftenseiten stellen eine Benutzeroberfläche bereit, zum Festlegen der Eigenschaften (oder die Methoden aufrufen) von einem oder mehreren COM-Objekten. Eigenschaftenseiten werden häufig von ActiveX-Steuerelementen verwendet, für das Bereitstellen von komplexe Benutzeroberflächen, mit die Steuerelementeigenschaften zur Entwurfszeit festgelegt werden können.  
  
 Eigenschaftenseiten sind COM-Objekte implementiert, die [IPropertyPage-Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/ms691246) oder [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) Schnittstelle. Diese Schnittstellen bieten die Methoden, mit denen die Seite zugeordnet werden können eine `site` (ein COM-Objekt, das den Container der Seite darstellt) und eine Reihe von *Objekte* (COM-Objekte, deren Methoden, als Reaktion auf Änderungen aufgerufen werden, vom Benutzer vorgenommene der Eigenschaftenseite "). Die Eigenschaft seitendatencontainer ist zuständig für das Aufrufen von Methoden auf der Benutzeroberfläche für die Eigenschaftenseite die Seite zu informieren, wenn vom Benutzer auf die zugrunde liegenden Objekte anzeigen oder Ausblenden der Benutzeroberfläche und beim Anwenden die Änderungen vorgenommen.  
  
 Jede Eigenschaftenseite kann vollständig unabhängig von den Objekten erstellt werden, dessen Eigenschaften festgelegt werden können. Alle ist eine Eigenschaftenseite benötigt, eine bestimmte Schnittstelle (oder ein Satz von Schnittstellen) zu verstehen und eine Benutzeroberfläche zum Aufrufen von Methoden für diese Schnittstelle bereitzustellen.  
  
 Weitere Informationen finden Sie unter [Eigenschaftenblätter und Eigenschaftenseiten](http://msdn.microsoft.com/library/windows/desktop/ms686577) in der [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Festlegen der Eigenschaftenseiten](../atl/specifying-property-pages.md)  
 Listet die Schritte zum Angeben von Eigenschaftenseiten für ein Steuerelement, und zeigt eine Beispielklasse.  
  
 [Implementieren der Eigenschaftenseiten](../atl/implementing-property-pages.md)  
 Listet die Schritte zum Implementieren von Eigenschaftenseiten, einschließlich der Methoden überschreiben. Führt Sie durch ein vollständiges Beispiel, das basierend auf dem ATLPages-Beispielprogramm.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ATLPages-Beispiel](../visual-cpp-samples.md)  
 Die abstrakte Beispiel für das ATLPages-Beispiel, das eine Eigenschaft mit implementiert `IPropertyPageImpl`.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)

