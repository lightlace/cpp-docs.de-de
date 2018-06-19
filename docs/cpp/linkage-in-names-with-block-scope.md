---
title: Verknüpfung in Namen mit Blockbereich | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- block scope [C++]
- external linkage, scope linkage rules
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab7758e962c028c4746836e470ee43eaab510f9e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418886"
---
# <a name="linkage-in-names-with-block-scope"></a>Verknüpfung in Namen mit Blockbereich
Die folgenden Bindungsregeln gelten für Namen mit Blockbereich (lokale Namen):  
  
-   Deklarierten Namen als `extern` haben externe Verknüpfung, es sei denn, die sie zuvor als deklariert wurden **statische**.  
  
-   Alle anderen Namen mit Blockgültigkeit haben keine Bindung.  
  
## <a name="see-also"></a>Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)