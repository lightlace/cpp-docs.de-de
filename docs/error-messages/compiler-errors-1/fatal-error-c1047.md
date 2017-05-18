---
title: Schwerwiegender Fehler C1047 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1047
dev_langs:
- C++
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: 5
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
ms.openlocfilehash: bee5dd89bf6ef92445466b12d79be5ba39d9cb5b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1047"></a>Schwerwiegender Fehler C1047
Die Objekt- oder Bibliotheksdatei 'datei' wurde mit einem älteren Compiler als andere Objekte erstellt. Erstellen Sie die alten Objekte und Bibliotheken neu.  
  
 C1047 wird ausgelöst, wenn Objektdateien oder Bibliotheken, die mit **/LTCG** erstellt wurden, miteinander verknüpft werden, die Objektdateien oder Bibliotheken aber mit verschiedenen Versionen des Visual C++-Toolsets erstellt wurden.  
  
 Dies kann auftreten, wenn Sie beginnen, eine neue Compilerversion zu verwenden, für vorhandene Objektdateien oder Bibliotheken aber keine Neuerstellung von Grund auf ausführen.  
  
 Um Fehler C1047 zu beheben, erstellen Sie alle Objektdateien und Bibliotheken neu.
