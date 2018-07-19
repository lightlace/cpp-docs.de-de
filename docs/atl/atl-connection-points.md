---
title: ATL-Verbindungspunkte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 179f4329d55261d71d3d122e6a2601ce7e805c0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354667"
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

