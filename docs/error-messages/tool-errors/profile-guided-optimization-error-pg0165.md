---
title: 'Profilgesteuerte Optimierung Fehler: PG0165 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PG0165
dev_langs: C++
helpviewer_keywords: PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32b9f5f3ee335aac0a8382377aa850c3b91a27a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimization-error-pg0165"></a>Fehler in profilgesteuerter Optimierung: PG0165
Lesen 'Dateiname.PGD': ' PGD-Version wird nicht unterstützt (Versionskonflikt) ".  
  
 PGD-Dateien sind spezifisch für ein bestimmtes Compilertoolset. Dieser Fehler wird generiert, wenn Sie einen anderen Compiler als die zum Verwenden *Filename*PGD. Dieser Fehler weist darauf hin, dass diese Compilertoolset nicht verwenden kann, die Daten aus *Filename*PGD zum Optimieren des aktuellen Programms.  
  
 Um dieses Problem zu beheben, Regenerieren *Filename*PGD mithilfe der aktuellen Compilertoolset.