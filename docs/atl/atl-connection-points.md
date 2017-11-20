---
title: ATL-Verbindungspunkte | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e0ef927ad6e2a0e9b0c71e211fa525ba7fc8ea0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="atl-connection-points"></a>ATL-Verbindungspunkte
Ein verbindungsfähiges Objekt ist eines, das Ausgangsschnittstellen unterstützt. Eine Ausgangsschnittstelle ermöglicht dem Objekt die Kommunikation mit einem Client. Für jede Ausgangsschnittstelle macht das verbindungsfähige Objekt einen Verbindungspunkt verfügbar. Jede Ausgangsschnittstelle wird von einem Client auf einem Objekt, das als Sink bezeichnet wird, implementiert.  
  
 ![Verbindungspunkte](../atl/media/vc2zw31.gif "vc2zw31")  
  
 Jeder Verbindungspunkt unterstützt die [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) Schnittstelle. Das verbindungsfähige Objekt macht seine Verbindungspunkte auf dem Client über die [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857) Schnittstelle.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ATL-Connection Point-Klassen](../atl/atl-connection-point-classes.md)  
 Beschreibt kurz die ATL-Klassen, die Verbindungspunkte unterstützen.  
  
 [Hinzufügen von Verbindungspunkten zu einem Objekt](../atl/adding-connection-points-to-an-object.md)  
 Beschreibt die Schritte, um einem Objekt Verbindungspunkte hinzuzufügen.  
  
 [Beispiel für ATL-Verbindungspunkt](../atl/atl-connection-point-example.md)  
 Enthält ein Beispiel für das Deklarieren eines Verbindungspunktes.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)

