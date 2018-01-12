---
title: Befehlszeilenfehler D8016 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D8016
dev_langs: C++
helpviewer_keywords: D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 463de86acf0446f125b66ec1cdc3768c6238b630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-error-d8016"></a>Befehlszeilenfehler D8016
'Option 1' und 'option2' Befehlszeilenoptionen sind nicht kompatibel  
  
 Die Befehlszeilenoptionen können nicht zusammen angegeben werden.  
  
 Überprüfen Sie die Umgebungsvariablen wie z. B. CL, Optionsangaben.  
  
 **"/ CLR"** impliziert **/EHa**, und Sie können angeben, alle anderen **/EH** Compileroption mit **"/ CLR"**. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Möglicherweise wird bei der Aktualisierung die Meldung D8016 eine [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0-Projekt: des Projekt-Assistent Updatevorgangs möglicherweise ermöglichen **/RTC** für jede Quelle-Codedatei im Projekt, überschreibt die der **/RTC** Einstellung für die Projekt.  Ändern Sie zur Behebung der **/RTC** für jede Quelle-Codedatei im Projekt auf die Standardeinstellung festlegen, d. h. die projekteinstellung für **/RTC** wird für jede Datei wirksam werden.  
  
 Finden Sie unter [/RTC (Run-Time Checks Fehler)](../../build/reference/rtc-run-time-error-checks.md) Informationen zum Ändern der **/RTC** Einstellung der Eigenschaft.