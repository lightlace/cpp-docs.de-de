---
title: Alloc_text | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
dev_langs: C++
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b54008652c036530135ca6d180398cb328fdb2da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="alloctext"></a>alloc_text
Namen des Codeabschnitts, in dem sich die angegebenen Funktionsdefinitionen befinden müssen. Das Pragma muss zwischen einem Funktionsdeklarator und der Funktionsdefinition für die benannten Funktionen auftreten.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Alloc_text** Pragma verarbeitet keine C++-Memberfunktionen oder überladene Funktionen. Es gilt nur für Funktionen mit C-Bindung deklariert wurden – d. h. Funktionen deklariert, mit der **Extern "C"** Verknüpfungsspezifikation. Wenn Sie versuchen, diese Pragma für eine Funktion mit C++-Bindung zu verwenden, wird ein Compilerfehler generiert.  
  
 Seit Funktion Adressierung mit `__based` wird nicht unterstützt, Angeben von abschnittsspeicherorten erfordert die Verwendung eines der **Alloc_text** Pragma. Indem der angegebene Name *Textsection* in doppelte Anführungszeichen eingeschlossen werden soll.  
  
 Die **Alloc_text** Pragma muss nach den Deklarationen aller angegebenen Funktionen und vor den Definitionen dieser Funktionen.  
  
 Funktionen, die auf die verwiesen wird einer **Alloc_text** Pragma sollte im selben Modul wie das Pragma definiert werden. Wenn dies nicht erfolgt ist und es wird eine nicht definierte Funktion später in einen anderen Textbereich kompiliert, ist ungewiss, ob der Fehler abgefangen wird. Obwohl das Programm in der Regel ordnungsgemäß ausgeführt wird, ist die Funktion nicht in den vorgesehenen Abschnitten zugeordnet.  
  
 Andere Einschränkungen für **Alloc_text** lauten wie folgt:  
  
-   Es kann nicht innerhalb einer Funktion verwendet werden.  
  
-   Es muss verwendet werden, nachdem die Funktion deklariert wurde, aber bevor die Funktion definiert wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)