---
title: Festlegen von Eigenschaftenseiten (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ISpecifyPropertyPages
dev_langs: C++
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a4519bee0d1f9c5e433114f12a6568bde6b8c4fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="specifying-property-pages"></a>Festlegen von Eigenschaftenseiten
Wenn Sie ein ActiveX-Steuerelement erstellen, sollten Sie häufig mit Eigenschaftenseiten zuordnen, die zum Festlegen der Eigenschaften des Steuerelements verwendet werden können. Steuern der Verwendung von Containern die **ISpecifyPropertyPages** Schnittstelle, um herauszufinden, welche Eigenschaftenseiten zum Festlegen der Eigenschaften des Steuerelements verwendet werden können. Sie müssen diese Schnittstelle für das Steuerelement zu implementieren.  
  
 Implementiert **ISpecifyPropertyPages** mit ATL, gehen Sie folgendermaßen vor:  
  
1.  Leiten Sie eine Klasse von [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).  
  
2.  Fügen Sie einen Eintrag für **ISpecifyPropertyPages** Ihre Klasse COM-Zuordnung.  
  
3.  Hinzufügen einer [PROP_PAGE](reference/property-map-macros.md#prop_page) Eintrag auf die eigenschaftszuordnung für jede Seite, die dem Steuerelement zugeordnet.  
  
> [!NOTE]
>  Beim Generieren von einem Standardsteuerelement mithilfe der [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md), Sie müssen nur hinzufügen der `PROP_PAGE` Einträge auf die eigenschaftszuordnung. Der Assistent generiert den erforderlichen Code für die anderen Schritte.  
  
 Gut konzipierte Container werden die angegebene Eigenschaftenseiten werden angezeigt, in der gleichen Reihenfolge wie die `PROP_PAGE` Einträge in der eigenschaftenzuordnung. Im Allgemeinen sollten Sie Standardeigenschaft seiteneinträge nach den Einträgen für Ihren benutzerdefinierten Seiten in der eigenschaftenzuordnung ablegen, sodass Benutzer auf das Steuerelement bestimmte Seiten zuerst angezeigt.  
  
## <a name="example"></a>Beispiel  
 Die folgende Klasse für einen Kalender steuern verwendet der **ISpecifyPropertyPages** Schnittstelle Container zu informieren, die die Eigenschaften mithilfe einer benutzerdefinierten Formatbezeichner für Datum und die vordefinierten Farbe Seite festgelegt werden können.  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../atl/atl-com-property-pages.md)   
 [ATLPages-Beispiel](../visual-cpp-samples.md)

