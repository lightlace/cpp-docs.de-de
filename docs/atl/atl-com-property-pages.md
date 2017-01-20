---
title: "ATL COM-Eigenschaftenseiten"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL COM-Objekte"
  - "ATL-Eigenschaftenseiten"
  - "COM-Objekte, ATL"
  - "COM-Eigenschaftenseiten"
  - "Eigenschaftenseiten, ATL"
  - "Eigenschaftenseiten, COM"
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ATL COM-Eigenschaftenseiten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM\-Eigenschaftenseiten stellen eine Benutzeroberfläche zum Festlegen der Eigenschaften \(oder durch Aufrufen der Methoden\) einer oder mehrerer COM\-Objekte bereit.  Eigenschaftenseiten werden extensiv von ActiveX\-Steuerelementen zum Bereitstellen von umfangreichen Benutzeroberflächen verwendet, die die zur Entwurfszeit ermöglichen festgelegt werden, Steuerelementeigenschaften.  
  
 Eigenschaftenseiten sind COM\-Objekte, die die [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) oder [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996)\-Schnittstelle implementieren.  Diese Schnittstellen stellen Methoden, die die mit ermöglichen `site` \(ein COM\-Objekt, das den Container der Seite darstellt\) und einigen *Objekten* \(COM\-Objekte, Seite zugeordnet werden, deren Methoden in Reaktion auf die Änderungen aufgerufen werden, die vom Benutzer der Eigenschaftenseite vorgenommen werden\).  Der Eigenschaftenseitencontainer ist für Aufrufe von Methoden auf der Eigenschaftenseitenschnittstelle verantwortlich, die Seite erkennt, wann die Benutzeroberfläche angezeigt oder ausgeblendet wird und wann die Änderungen an, die vom Benutzer an den zugrunde liegenden Objekten vorgenommen werden.  
  
 Jede Eigenschaftenseite kann unabhängig von Objekte vollständig erstellt werden, deren Eigenschaften festgelegt werden können.  Alles, was eine Eigenschaftenseite erfordert, ist, eine bestimmte Schnittstelle \(oder Satz von Schnittstellen\) zu verstehen und eine Benutzeroberfläche für Aufrufe von Methoden für diese Schnittstelle bereitzustellen.  
  
 Weitere Informationen finden Sie unter [Eigenschaftenblätter und Eigenschaftenseiten](http://msdn.microsoft.com/library/windows/desktop/ms686577) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## In diesem Abschnitt  
 [Angeben von Eigenschaftenseiten](../atl/specifying-property-pages.md)  
 Führt die Schritte zum Angeben von Eigenschaftenseiten für Sie Steuerelement auf und zeigt eine Beispielklasse an.  
  
 [Implementieren von Eigenschaftenseiten](../atl/implementing-property-pages.md)  
 Führt die Schritte zum Implementieren von Eigenschaftenseiten, einschließlich Methoden, um auf zu überschreiben.  Führt Sie durch ein vollständiges Beispiel auf dem ATLPages\-Beispielprogramm.  
  
## Verwandte Abschnitte  
 [ATLPages\-Beispiel](../top/visual-cpp-samples.md)  
 Die Beispielzusammenfassung für das ATLPages\-Beispiel, das eine Eigenschaftenseite mit `IPropertyPageImpl` implementiert.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen darüber, wie mit Active Template Library Programmierung.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)