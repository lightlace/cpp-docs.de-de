---
title: Aggregation | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 760a595274ba7a1901138cc0cceceddf97122725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32353962"
---
# <a name="aggregation"></a>Aggregation
Es gibt Situationen, wenn Implementierer eines Objekts einem anderen Objekt vorgefertigten angebotenen Dienste zu nutzen möchten. Darüber hinaus möchte er dieses zweite Objekt als eine natürliche Teil des ersten angezeigt werden. COM erreicht beide Ziele durch Kapselung und Aggregation.  
  
 Aggregation bedeutet, dass der enthaltenden Objekts (äußeren) die darin enthaltenen Objekte (innere) im Rahmen der Erstellung erstellt und die Schnittstellen des inneren Objekts werden von der äußeren verfügbar gemacht. Ein Objekt kann sich selbst oder nicht aggregierbar sein. Wenn dies der Fall, müssen sie bestimmte Regeln für die Aggregation ordnungsgemäß funktioniert entsprechen.  
  
 In erster Linie für alle **IUnknown** -Methodenaufrufe der darin enthaltenen Objekte auf das enthaltende Objekt delegieren müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Wiederverwenden von Objekten](http://msdn.microsoft.com/library/windows/desktop/ms678443)

