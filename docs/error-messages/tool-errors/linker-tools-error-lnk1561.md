---
title: Linkertoolfehler Lnk1561 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: fbc63a58cd4e276aa2a3f77baeea07d1912eda98
ms.lasthandoff: 04/24/2017

---
# <a name="linker-tools-error-lnk1561"></a>Linkertoolfehler LNK1561
Einstiegspunkt muss definiert werden.  
  
Der Linker wurde einen Einstiegspunkt nicht gefunden werden. Dieser Fehler kann mehrere Ursachen haben:  
-   Sie können nicht die Datei aufgenommen haben, die Ihr Ausgangspunkt, in der Liste der Dateien für eine Verknüpfung definiert. Stellen Sie sicher, dass die Datei, die Einstiegspunktfunktion enthält, in Ihrer app verknüpft ist.  
-   Möglicherweise ist den Einstiegspunkt mit der falschen Funktions-Signatur definierten; z. B. Sie möglicherweise besitzen falsch geschrieben oder die falschen Groß-/Kleinschreibung für den Namen der Funktion verwendet, oder der Rückgabetyp oder Parametertyp auf falsch angegeben. Wird standardmäßig der Linker sucht nach einem `main` oder `wmain` -Funktion für eine Konsolen-app eine `WinMain` oder `wWinMain` -Funktion für eine Windows-app oder `DllMain` für eine DLL, die die Initialisierung sind erforderlich.  
-   Sie können nicht angegeben haben die [/DLL](../../build/reference/dll-build-a-dll.md) option beim Erstellen einer DLL.  
-   Möglicherweise haben den Namen der Einstiegspunktfunktion nicht korrekt angegeben bei der Verwendung der [/Entry](../../build/reference/entry-entry-point-symbol.md) (Linkeroption).  
-   Bei Verwendung der [LIB](../../build/reference/lib-reference.md) Tools, um eine DLL erstellen, Sie haben eine DEF-Datei angegeben. Wenn dies der Fall ist, entfernen Sie die DEF-Datei aus dem Build.    
  
Wenn Sie eine app zu erstellen, der Linker sucht nach einer *Einstiegspunkt*, die Funktion aufgerufen wird, um Ihren Code zu starten. Dies ist die Funktion, die aufgerufen wird, nachdem die app geladen wird und die Common Language Runtime initialisiert wird. Sie müssen eine Einstiegspunktfunktion für eine app bereitstellen, oder Ihre app nicht ausgeführt. Ein Einstiegspunkt ist optional für eine DLL. Standardmäßig sucht der Linker eine Einstiegspunktfunktion, das eins der zahlreichen bestimmte Namen und Signaturen, wie z. B. besitzt `int main(int, char**)`. Sie können einen anderen Funktionsnamen angeben, als Eintrag Punkt mit der/Entry (Linkeroption).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK1561 generiert:  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```
