---
title: Schwerwiegender Fehler C1099 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1099
dev_langs:
- C++
helpviewer_keywords:
- C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 74ef24f35084e76d6f8ad9d3eec3459e7f50a930
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1099"></a>Schwerwiegender Fehler C1099
Kompilierungsabbruch durch Modul für Bearbeiten und Fortfahren  
  
 Durch Bearbeiten und Fortfahren wurde eine vorkompilierte Headerdatei in Vorbereitung für das Kompilieren von Codeänderungen geladen, aber nachfolgende Maßnahmen (z. B. Codeänderungen vor der vorkompilierten `#include` -Headeranweisung oder das Beenden des Debuggers) verhindern, dass die Kompilierung mit diesem Prozess von „Bearbeiten und Fortfahren“ beendet wird. Sie müssen keine Maßnahmen ergreifen, um diesen Fehler zu beheben.
