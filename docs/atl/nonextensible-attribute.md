---
title: nonextensible-Attribut | Microsoft Docs
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
ms.openlocfilehash: 40b4b79701862ca07e704aca098419479923ef1a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355632"
---
# <a name="nonextensible-attribute"></a>nonextensible-Attribut
Wenn eine duale Schnittstelle zur Laufzeit nicht erweitert wird (d. h. Sie wird nicht bereitstellen, Methoden oder Eigenschaften über **IDispatch:: Invoke** , die nicht über die Vtable verfügbar sind), sollten Sie übernehmen die **nonextensible** -Attribut auf die Schnittstellendefinition. Dieses Attribut stellt die Informationen zu Clientsprachen (z. B. Visual Basic), die zum Aktivieren der codeüberprüfung der vollständige zum Zeitpunkt der Kompilierung verwendet werden kann. Wenn dieses Attribut nicht angegeben wird, können Fehler im Clientcode bleiben bis zur Laufzeit ausgeblendet.  
  
 Weitere Informationen zu den **nonextensible** Attribut und ein Beispiel finden Sie unter [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)

