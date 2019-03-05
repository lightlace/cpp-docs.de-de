---
title: Festlegen der Eigenschaftenseiten (ATL)
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPages
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
ms.openlocfilehash: d738759dfba50f26b788ee1b0761baf8bc4b00ab
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287132"
---
# <a name="specifying-property-pages"></a>Festlegen der Eigenschaftenseiten

Wenn Sie ein ActiveX-Steuerelement erstellen, möchten Sie häufig Eigenschaftenseiten zugeordnet werden, die zum Festlegen der Eigenschaften des Steuerelements verwendet werden können. Steuern der Container die `ISpecifyPropertyPages` Schnittstelle, um herauszufinden, welche Eigenschaftenseiten verwendet werden können, um die Eigenschaften des Steuerelements festzulegen. Sie müssen diese Schnittstelle für das Steuerelement zu implementieren.

Zum Implementieren `ISpecifyPropertyPages` mit ATL, gehen Sie folgendermaßen vor:

1. Leiten Sie eine Klasse von [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).

1. Fügen Sie einen Eintrag für `ISpecifyPropertyPages` COM-Zuordnung Ihrer Klasse fest.

1. Hinzufügen einer [PROP_PAGE](reference/property-map-macros.md#prop_page) einen Eintrag in der eigenschaftenzuordnung für jede Seite, die mit Ihrem Steuerelement verknüpft ist.

> [!NOTE]
> Beim Generieren von einem Standardsteuerelement mithilfe der [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md), Sie müssen nur die eigenschaftenzuordnung PROP_PAGE Einträge hinzugefügt. Der Assistent generiert den erforderlichen Code für den weiteren Schritten.

Konzipierten Container werden die angegebene Eigenschaftenseiten in der gleichen Reihenfolge wie die PROP_PAGE Einträge in der eigenschaftenzuordnung angezeigt. Im Allgemeinen sollten Sie seiteneinträge Standardeigenschaft nach den Einträgen für Ihre benutzerdefinierten Seiten in der eigenschaftenzuordnung abgelegt, damit Benutzer die Seiten, die spezifisch für das Steuerelement zuerst angezeigt.

## <a name="example"></a>Beispiel

Die folgende Klasse für einen Kalender steuern verwendet der `ISpecifyPropertyPages` Schnittstelle, um Container zu informieren, die die Eigenschaften können mithilfe einer benutzerdefinierten Datums- und die vordefinierten Farbe-Seite festgelegt werden.

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../atl/atl-com-property-pages.md)<br/>
[ATLPages-Beispiel](../visual-cpp-samples.md)
