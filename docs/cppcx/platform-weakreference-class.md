---
title: 'Platform:: WeakReference-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59d87d2e00ef567c0273e71410ad58ebf0a5c061
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="platformweakreference-class"></a>Platform::WeakReference-Klasse
Stellt einen schwachen Verweis auf eine Instanz einer Verweisklasse dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp 
class WeakReference  
```  
  
#### <a name="parameters"></a>Parameter  
  
### <a name="members"></a>Member  
  
### <a name="constructors"></a>Konstruktoren  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[WeakReference::WeakReference](#ctor)|Initialisiert eine neue Instanz der WeakReference-Klasse.|  
  
### <a name="methods"></a>Methoden  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[WeakReference::Resolve](#resolve)|Gibt einen Handle zur zugrunde liegenden Verweisklasse oder nullptr zurück, wenn das Objekt nicht mehr vorhanden ist.|  
  
### <a name="operators"></a>Operatoren  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[WeakReference::operator=](#operator-assign)|Weist dem WeakReference-Objekt einen neuen Wert zu.|  
|[WeakReference::operator-BoolType](#booltype)|Implementiert das sichere boolesche Muster.|  
  
### <a name="remarks"></a>Hinweise  
 Die WeakReference-Klasse selbst ist keine Verweisklasse und erbt daher nicht von Platform::Object^ und kann nicht in der Signatur einer öffentlichen Methode verwendet werden.  

## <a name="operator-assign"></a> WeakReference =
Weist einem schwachen Verweis einen Wert zu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));    
WeakReference& operator=(const WeakReference& otherArg);   
WeakReference& operator=(WeakReference&& otherArg);    
WeakReference& operator=(const volatile ::Platform::Object^ const otherArg); 
```  
  
### <a name="remarks"></a>Hinweise  
 Die letzte Überladung in der Liste oben ermöglicht es Ihnen, einer WeakReference-Variable eine Verweisklasse zuzuweisen. In diesem Fall wird die Umwandlung zu [Platform:: Object](../cppcx/platform-object-class.md)^. Sie wiederherstellen den ursprünglichen Typ später durch Angabe als Argument für den Typparameter in der [WeakReference:: Resolve\<T >](#resolve) Memberfunktion.  
  
## <a name="booltype"></a> WeakReference-BoolType
Implementiert das sichere boolesche Muster für die WeakReference-Klasse. Nicht explizit vom Code aufzurufen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
BoolType BoolType()  
```  

## <a name="resolve"></a> WeakReference:: Resolve-Methode (Plattform-Namespace)
Gibt einen Handle zur ursprünglichen Verweisklasse oder `nullptr` zurück, wenn das Objekt nicht mehr vorhanden ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
template<typename T>  
T^ Resolve() const  
```  
  
### <a name="parameters"></a>Parameter  
  
### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein Handle zur Verweisklasse, der das WeakReference-Objekt bereits zugeordnet wurde, oder nullptr.  
  
### <a name="example"></a>Beispiel  
 Dies ist die Beschreibung für ein Codebeispiel.  
  
```  
  
Bar^ bar = ref new Bar();  
//use bar...  
  
if (bar != nullptr)  
{  
    WeakReference wr(bar);  
    Bar^ newReference = wr.Resolve<Bar>();  
}  
```  
  
 Beachten Sie, dass der Typparameter T und nicht T^ ist.  
  
 
## <a name="ctor"></a> WeakReference:: WeakReference-Konstruktor
Bietet verschiedene Möglichkeiten, einen schwachen Verweis zu erstellen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& otherArg);  
WeakReference(WeakReference&& otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const otherArg);  
```  
### <a name="example"></a>Beispiel  
  
```cpp    
MyClass^ mc = ref new MyClass();  
WeakReference wr(mc);  
MyClass^ copy2 = wr.Resolve<MyClass>();    
```  
  
## <a name="see-also"></a>Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)