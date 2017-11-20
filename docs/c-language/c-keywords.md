---
title: "C-Schlüsselwörter | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 71e5c715c6065e8c05466bc3f09eba57606b304e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="c-keywords"></a>C-Schlüsselwörter
"Schlüsselwörter" sind Wörter, die eine besondere Bedeutung für den C-Compiler haben. In den Übersetzungsphasen 7 und 8 kann ein Bezeichner nicht dieselbe Schreibweise und Groß-/Kleinschreibung haben wie ein C-Schlüsselwort. (Eine Beschreibung der [Übersetzungsphasen](../preprocessor/phases-of-translation.md) finden Sie in der *Präprozessorreferenz*. Informationen zu Bezeichnern finden Sie unter [Bezeichner](../c-language/c-identifiers.md).) Die Programmiersprache C verwendet die folgenden Schlüsselwörter:  
  
|||||  
|-|-|-|-|  
|**auto**|**double**|**int**|**struct**|  
|**break**|**else**|**long**|**switch**|  
|**case**|**enum**|**register**|**typedef**|  
|**char**|**extern**|**return**|**union**|  
|**const**|**float**|**short**|**unsigned**|  
|**continue**|**for**|**signed**|**void**|  
|**default**|**goto**|**sizeof**|**volatile**|  
|**do**|**if**|**static**|**while**|  
  
 Sie können Schlüsselwörter nicht neu definieren. Bevor Sie mit [C-Präprozessoranweisungen](../preprocessor/preprocessor-directives.md) kompilieren, können Sie jedoch Ersatztext für Schlüsselwörter angeben.  
  
 **Microsoft-spezifisch**  
  
 Der ANSI C-Standard ermöglicht, dass Bezeichner mit zwei vorangestellten Unterstrichen für Compilerimplementierungen reserviert werden können. Daher werden gemäß Microsoft-Konvention Microsoft-spezifischen Schlüsselwortnamen doppelte Unterstriche vorangestellt. Diese Wörter können nicht als Bezeichnernamen verwendet werden. Eine Beschreibung der ANSI-Regeln für die Benennung von Bezeichnern, einschließlich der Verwendung von doppelten Unterstrichen, finden Sie unter [Bezeichner](../c-language/c-identifiers.md).  
  
 Die folgenden Schlüsselwörter und speziellen Bezeichner werden vom Microsoft C-Compiler erkannt:  
  
|||||  
|-|-|-|-|  
|**__asm**|**dllimport**2|**__int8**|**naked**2|  
|**__based**1|**__except**|**__int16**|**__stdcall**|  
|**__cdecl**|**__fastcall**|**__int32**|**thread**2|  
|**__declspec**|**__finally**|**__int64**|**__try**|  
|**dllexport**2|**__inline**|**__leave**||  
  
 1. Das **__based**-Schlüsselwort weist eingeschränkte Verwendung für 32-Bit- und 64-Bit-Zielkompilierungen auf.  
  
 2. Dies sind spezielle Bezeichner, wenn sie mit **__declspec** verwendet werden. Ihre Verwendung in anderen Kontexten ist nicht eingeschränkt.  
  
 Standardmäßig sind Microsoft-Erweiterungen aktiviert. Um sicherzustellen, dass die Programme vollständig übertragbar sind, können Sie Microsoft-Erweiterungen durch Angeben der Option "/Za" (Kompilieren für ANSI-Kompatibilität) während der Kompilierung deaktivieren. Dabei werden Microsoft-spezifische Schlüsselwörter deaktiviert.  
  
 Wenn Microsoft-Erweiterungen aktiviert sind, können Sie in den Programmen die oben aufgeführten Schlüsselwörter verwenden. Bei Einhaltung der ANSI-Kompatibilität werden den meisten dieser Schlüsselwörter ein doppelten Unterstrich vorangestellt. Die vier Ausnahmen – **dllimport**, **dllimport**, **naked** und **thread** werden nur mit **__declspec** verwendet und erfordern deshalb keinen vorangestellten doppelten Unterstrich. Für die Abwärtskompatibilität werden die restlichen Schlüsselwörter mit Versionen mit einem Unterstrich unterstützt.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Elemente](../c-language/elements-of-c.md)