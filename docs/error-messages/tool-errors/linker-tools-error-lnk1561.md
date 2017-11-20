---
title: Linkertoolfehler Lnk1561 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: f918c51e6f4539c020bc59ad28c867f8e2d1ae75
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk1561"></a>Linkertoolfehler LNK1561
Einstiegspunkt muss definiert werden.  
  
Der Linker wurde nicht gefunden. ein *Einstiegspunkt*, die erste Funktion in der ausführbaren Datei aufrufen. Wird standardmäßig der Linker sucht nach einem `main` oder `wmain` -Funktion für eine Konsolen-app eine `WinMain` oder `wWinMain` -Funktion für eine Windows-app oder `DllMain` für eine DLL, die die Initialisierung sind erforderlich. Sie können eine andere Funktion angeben, mit der [/Entry](../../build/reference/entry-entry-point-symbol.md) (Linkeroption).  
  
Dieser Fehler kann mehrere Ursachen haben:  
-   Sie können nicht die Datei aufgenommen haben, die Ihr Ausgangspunkt, in der Liste der Dateien für eine Verknüpfung definiert. Stellen Sie sicher, dass die Datei, die Einstiegspunktfunktion enthält, in Ihrer app verknüpft ist.  
-   Möglicherweise ist den Einstiegspunkt mit der falschen Funktions-Signatur definierten; z. B. Sie möglicherweise besitzen falsch geschrieben oder die falschen Groß-/Kleinschreibung für den Namen der Funktion verwendet, oder der Rückgabetyp oder Parametertyp auf falsch angegeben.  
-   Sie können nicht angegeben haben die [/DLL](../../build/reference/dll-build-a-dll.md) option beim Erstellen einer DLL.  
-   Möglicherweise haben den Namen der Einstiegspunktfunktion nicht korrekt angegeben bei der Verwendung der [/Entry](../../build/reference/entry-entry-point-symbol.md) (Linkeroption).  
-   Bei Verwendung der [LIB](../../build/reference/lib-reference.md) Tools, um eine DLL erstellen, Sie haben eine DEF-Datei angegeben. Wenn dies der Fall ist, entfernen Sie die DEF-Datei aus dem Build.    
  
Wenn Sie eine app zu erstellen, sucht der Linker eine Einstiegspunktfunktion aufrufen, um den Code zu starten. Dies ist die Funktion, die aufgerufen wird, nachdem die app geladen wird und die Common Language Runtime initialisiert wird. Sie müssen eine Einstiegspunktfunktion für eine app bereitstellen, oder Ihre app nicht ausgeführt. Ein Einstiegspunkt ist optional für eine DLL. Standardmäßig sucht der Linker eine Einstiegspunktfunktion, das eins der zahlreichen bestimmte Namen und Signaturen, wie z. B. besitzt `int main(int, char**)`. Sie können einen anderen Funktionsnamen angeben, als Eintrag Punkt mit der/Entry (Linkeroption).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK1561 generiert:  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```