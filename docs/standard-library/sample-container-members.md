---
title: Sample Container-Member | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- container classes
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dcb72cd50bf51543bc5fba29c2add21e4d2d8b15
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="sample-container-members"></a>Sample Container-Member

> [!NOTE]
> Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

## <a name="reference"></a>Referenz

## <a name="typedefs"></a>Typedefs

|||
|-|-|
|[const_iterator](../standard-library/container-class-const-iterator.md)|Beschreibt ein Objekt, das als konstanter Iterator für die gesteuerte Sequenz fungieren kann.|
|[const_reference](../standard-library/container-class-const-reference.md)|Beschreibt ein Objekt, das als konstanter Verweis auf ein Element der gesteuerten Sequenz fungieren kann.|
|[const_reverse_iterator](../standard-library/container-class-const-reverse-iterator.md)|Beschreibt ein Objekt, das als konstanter Reverse-Iterator für die gesteuerte Sequenz fungieren kann.|
|[difference_type](../standard-library/container-class-difference-type.md)|Beschreibt ein Objekt, das die Differenz zwischen den Adressen von zwei beliebigen Elementen in der gesteuerten Sequenz darstellen kann.|
|[Iterator](../standard-library/container-class-iterator.md)|Beschreibt ein Objekt, das als Iterator für die gesteuerte Sequenz fungieren kann.|
|[Verweis](../standard-library/container-class-reference.md)|Beschreibt ein Objekt, das als Verweis auf ein Element der gesteuerten Sequenz fungieren kann.|
|[reverse_iterator](../standard-library/container-class-reverse-iterator.md)|Beschreibt ein Objekt, das als Reverse-Iterator für die gesteuerte Sequenz fungieren kann.|
|[size_type](../standard-library/container-class-size-type.md)|Beschreibt ein Objekt, das die Länge einer beliebigen gesteuerten Sequenz darstellen kann.|
|[value_type](../standard-library/container-class-value-type.md)|Dient als ein Synonym für den Vorlagenparameter **Ty**.|

## <a name="member-functions"></a>Memberfunktionen

|||
|-|-|
|[begin](../standard-library/container-class-begin.md)|Gibt einen Iterator zurück, der auf das erste Element der Sequenz zeigt (bzw. unmittelbar hinter das Ende einer leeren Sequenz).|
|[clear](../standard-library/container-class-clear.md)|Ruft [erase](../standard-library/container-class-erase.md)([begin](../standard-library/container-class-begin.md), [end](../standard-library/container-class-end.md)) auf.|
|[empty](../standard-library/container-class-empty.md)|Gibt **TRUE** für eine leere gesteuerte Sequenz zurück.|
|[end](../standard-library/container-class-end.md)|Gibt einen Iterator zurück, der direkt hinter das Ende der Sequenz verweist.|
|[erase](../standard-library/container-class-erase.md)|Löscht ein Element.|
|[max_size](../standard-library/container-class-max-size.md)|Gibt die Länge der längsten Sequenz zurück, die das Objekt in konstanter Zeit und unabhängig von der Länge der gesteuerten Sequenz steuern kann.|
|[rbegin](../standard-library/container-class-rbegin.md)|Gibt einen Reverse-Iterator zurück, der auf die Position unmittelbar hinter dem Ende der gesteuerten Sequenz zeigt und den Anfang der umgekehrten Sequenz festlegt.|
|[rend](../standard-library/container-class-rend.md)|Die Memberfunktion gibt einen Reverse-Iterator zurück, der auf das erste Element der Sequenz zeigt (bzw. unmittelbar hinter das Ende einer leeren Sequenz) und das Ende der umgekehrte Sequenz festlegt.|
|[size](../standard-library/container-class-size.md)|Gibt die Länge der gesteuerten Sequenz zurück, in konstanter Zeit und unabhängig von der Länge der gesteuerten Sequenz.|
|[swap](../standard-library/container-class-swap.md)
