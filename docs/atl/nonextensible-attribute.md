---
title: nonextensible-Attribut | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73edae463051aca3ecafac53ae6200df103b8d90
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762140"
---
# <a name="nonextensible-attribute"></a>nonextensible-Attribut

Wenn eine duale Schnittstelle zur Laufzeit nicht erweitert wird (d. h. Sie wird nicht angeben, Methoden oder Eigenschaften über `IDispatch::Invoke` , die nicht über die Vtable verfügbar sind), gelten die **nonextensible** Attribut zu Ihrer Schnittstelle die Definition. Dieses Attribut stellt die Informationen zur Clientsprachen (z. B. Visual Basic), die zum Aktivieren der Überprüfung der vollständigen Code zum Zeitpunkt der Kompilierung verwendet werden kann. Wenn dieses Attribut nicht angegeben wird, möglicherweise Fehler im Clientcode bleiben bis zur Laufzeit ausgeblendet.

Weitere Informationen zu den **nonextensible** -Attribut und ein Beispiel finden Sie unter [nonextensible](../windows/nonextensible.md).

## <a name="see-also"></a>Siehe auch

[Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)

