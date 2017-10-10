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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b848f874f382e3d4f944a7eb372db9dcc5011f59
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1047"></a>Schwerwiegender Fehler C1047
Die Objekt- oder Bibliotheksdatei 'datei' wurde mit einem älteren Compiler als andere Objekte erstellt. Erstellen Sie die alten Objekte und Bibliotheken neu.  
  
 C1047 wird ausgelöst, wenn Objektdateien oder Bibliotheken, die mit **/LTCG** erstellt wurden, miteinander verknüpft werden, die Objektdateien oder Bibliotheken aber mit verschiedenen Versionen des Visual C++-Toolsets erstellt wurden.  
  
 Dies kann auftreten, wenn Sie beginnen, eine neue Compilerversion zu verwenden, für vorhandene Objektdateien oder Bibliotheken aber keine Neuerstellung von Grund auf ausführen.  
  
 Um Fehler C1047 zu beheben, erstellen Sie alle Objektdateien und Bibliotheken neu.
