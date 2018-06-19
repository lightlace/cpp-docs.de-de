---
title: Postfix-Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14a23da2e8ed41954bd6faa2803d6e6c7dfb37a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384384"
---
# <a name="postfix-operators"></a>Postfix-Operatoren
Die Postfix-Operatoren weisen den höchsten Rang (die festeste Bindung) in der Ausdrucksauswertung auf.  
  
## <a name="syntax"></a>Syntax  
 *postfix-expression*:  
 *primary-expression*  
  
 *postfix-expression*  **[**  *expression*  **]**  
  
 *postfix-expression* **(** *argument-expression-list* -Opt **)**  
  
 *postfix-expression*  **.**  *identifier*  
  
 *postfix-expression*  **->**  *identifier*  
  
 *postfix-expression* **++**  
  
 *postfix-expression* **--**  
  
 Operatoren in dieser Rangfolgenebene sind die Arrayfeldindizes, Funktionsaufrufe, die Struktur- und Union-Member sowie Postfix-Operatoren für Inkrement und Dekrement.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Operatoren](../c-language/c-operators.md)