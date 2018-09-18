---
title: Festlegen der Eigenschaftenseiten (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ISpecifyPropertyPages
dev_langs:
- C++
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db0445e83bbcae6baa45d4a482489e6761fa945a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069429"
---
# <a name="specifying-property-pages"></a>Festlegen der Eigenschaftenseiten

Wenn Sie ein ActiveX-Steuerelement erstellen, möchten Sie häufig Eigenschaftenseiten zugeordnet werden, die zum Festlegen der Eigenschaften des Steuerelements verwendet werden können. Steuern der Container die `ISpecifyPropertyPages` Schnittstelle, um herauszufinden, welche Eigenschaftenseiten verwendet werden können, um die Eigenschaften des Steuerelements festzulegen. Sie müssen diese Schnittstelle für das Steuerelement zu implementieren.

Zum Implementieren `ISpecifyPropertyPages` mit ATL, gehen Sie folgendermaßen vor:

1. Leiten Sie eine Klasse von [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).

2. Fügen Sie einen Eintrag für `ISpecifyPropertyPages` COM-Zuordnung Ihrer Klasse fest.

3. Hinzufügen einer [PROP_PAGE](reference/property-map-macros.md#prop_page) einen Eintrag in der eigenschaftenzuordnung für jede Seite, die mit Ihrem Steuerelement verknüpft ist.

> [!NOTE]
>  Beim Generieren von einem Standardsteuerelement mithilfe der [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md), Sie müssen nur die eigenschaftenzuordnung PROP_PAGE Einträge hinzugefügt. Der Assistent generiert den erforderlichen Code für den weiteren Schritten.

Konzipierten Container werden die angegebene Eigenschaftenseiten in der gleichen Reihenfolge wie die PROP_PAGE Einträge in der eigenschaftenzuordnung angezeigt. Im Allgemeinen sollten Sie seiteneinträge Standardeigenschaft nach den Einträgen für Ihre benutzerdefinierten Seiten in der eigenschaftenzuordnung abgelegt, damit Benutzer die Seiten, die spezifisch für das Steuerelement zuerst angezeigt.

## <a name="example"></a>Beispiel

Die folgende Klasse für einen Kalender steuern verwendet der `ISpecifyPropertyPages` Schnittstelle, um Container zu informieren, die die Eigenschaften können mithilfe einer benutzerdefinierten Datums- und die vordefinierten Farbe-Seite festgelegt werden.

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../atl/atl-com-property-pages.md)<br/>
[ATLPages-Beispiel](../visual-cpp-samples.md)

