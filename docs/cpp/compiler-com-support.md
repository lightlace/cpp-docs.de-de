---
title: Compiler COM-Support | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d81c54f7af604024da852999ca78fa5ee55079ef
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support"></a>COM-Unterstützung des Compilers
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Der Visual C++-Compiler kann COM(Component Object Model)-Typbibliotheken direkt lesen und den Inhalt in C++-Quellcode übersetzen, der in die Kompilierung aufgenommen werden kann. Es sind Spracherweiterungen verfügbar, um die COM-Programmierung auf der Clientseite zu erleichtern.  
  
 Mithilfe der [#import-Präprozessordirektive](../preprocessor/hash-import-directive-cpp.md), der Compiler eine Typbibliothek lesen und konvertiert ihn in eine C++-Headerdatei, die beschreibt, die COM-als Schnittstellen Klassen. Ein Satz von `#import`-Attributen ist für die Benutzersteuerung des Inhalts der resultierenden Typbibliothek-Headerdateien verfügbar.  
  
 Können Sie die [__declspec](../cpp/declspec.md) erweitertes Attribut [Uuid](../cpp/uuid-cpp.md) ein COM-Objekt einen global eindeutigen Bezeichner (GUID) zuweisen. Das Schlüsselwort [__uuidof](../cpp/uuidof-operator.md) können verwendet werden, um ein COM-Objekt zugeordnete GUID zu extrahieren. Eine andere `__declspec` Attribut [Eigenschaft](../cpp/property-cpp.md), kann verwendet werden, um anzugeben der **abrufen** und **festgelegt** Methoden für einen Datenmember eines COM-Objekts.  
  
 Ein Satz von COM-unterstützungs-Funktionen und Klassen dient zur Unterstützung der **VARIANT** und `BSTR` Typen, implementieren Sie intelligente Zeiger und das Fehlerobjekt zu kapseln, die von ausgelöst `_com_raise_error`:  
  
-   [Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)  
  
-   [_bstr_t](../cpp/bstr-t-class.md)  
  
-   [_com_error](../cpp/com-error-class.md)  
  
-   [_com_ptr_t](../cpp/com-ptr-t-class.md)  
  
-   [_variant_t](../cpp/variant-t-class.md)  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Compiler-COM-Unterstützungsklassen](../cpp/compiler-com-support-classes.md)   
 [Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)
