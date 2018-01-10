---
title: '-Zc: Auto (Variablentyp ableiten) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:auto
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd2f0ff353e1243685c94da0c28f29e810b2a9ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (Variablentyp ableiten)
Die **/Zc: Auto [-]** Compileroption teilt dem Compiler mit, wie Sie die [auto-Schlüsselwort](../../cpp/auto-keyword.md) um Variablen zu deklarieren. Wenn Sie die Standardoption angeben **/Zc: Auto**, leitet der Compiler den Typ der deklarierten Variable vom entsprechenden Initialisierungsausdruck. Bei Angabe von **/Zc:auto-**, ordnet der Compiler die Variable der automatischen Speicherklasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zc:auto[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Der C++-Standard definiert eine ursprüngliche und eine überarbeitete Bedeutung für das `auto`-Schlüsselwort. Vor dem [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], das-Schlüsselwort deklariert eine Variable in der automatischen Speicherklasse, d. h. eine Variable, die verfügt über eine lokalen Lebensdauer. Beginnend mit [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], das Schlüsselwort leitet den Typ einer Variablen aus der Deklaration Initialisierungsausdruck. Verwenden Sie die **/Zc: Auto [-]** Compileroption, um den Compiler aufzufordern, verwenden Sie die ursprünglichen oder überarbeitete Bedeutung von der `auto` Schlüsselwort.  
  
 Der Compiler gibt eine entsprechende Diagnosemeldung aus, wenn Ihre Verwendung des `auto`-Schlüsselworts der aktuellen Compileroption widerspricht. Weitere Informationen finden Sie unter [auto-Schlüsselwort](../../cpp/auto-keyword.md). Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [nicht standardmäßigem Verhalten](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Konfigurationseigenschaften** Knoten.  
  
3.  Klicken Sie auf die **C/C++-** Knoten.  
  
4.  Klicken Sie auf die **Befehlszeile** Knoten.  
  
5.  Hinzufügen **/Zc: Auto** oder **/Zc:auto-** auf die **zusätzliche Optionen:** Bereich.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)   
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)