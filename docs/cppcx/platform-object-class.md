---
title: 'Platform:: Object-Klasse | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
dev_langs:
- C++
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a7fc6dc1df1d1e22032dbe7322b9a6ead8334ddc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="platformobject-class"></a>Platform::Object-Klasse
Stellt gemeinsames Verhalten für Verweisklassen und referenzstrukturen in Windows-Runtime-apps bereit. Alle Verweisklassen- und Referenzstruktur-Instanzen sind implizit konvertierbar in Platform::Object^ und können seine virtuelle ToString-Methode überschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class Object : Object  
```  
  
### <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Object:: Object](#ctor)|Initialisiert eine neue Instanz der Objektklasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Object:: Equals](#equals)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|  
|[Object:: GetHashCode](#gethashcode)|Gibt den Hashcode für diese Instanz zurück.|  
|[Object:: ReferenceEquals](#referenceequals)|Stellt fest, ob die angegebenen Objekt-Instanzen dieselbe Instanz sind.|  
|[ToString](#tostring)|Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt. Kann überschrieben werden.|  
|[GetType](#gettype)|Ruft einen [Platform::Type](../cppcx/platform-type-class.md) ab, der die aktuelle Instanz beschreibt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Object`  
  
 `Object`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  

  
## <a name="equals"></a> Object:: Equals-Methode
Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
### <a name="parameters"></a>Parameter  
 obj  
 Das zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` , wenn die Objekte gleich sind, andernfalls `false`.  
  


## <a name="gethashcode"></a>  Object:: GetHashCode-Methode
Gibt den `IUnknown`*-Identitätswert für diese Instanz zurück, wenn es sich um ein COM-Objekt handelt, bzw. einen berechneten Hashwert, wenn es kein COM-Objekt ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein numerischer Wert, der das Objekt eindeutig identifiziert.  
  
### <a name="remarks"></a>Hinweise  
 Sie können GetHashCode zum Erstellen von Schlüsseln für Objekte in Zuordnungen verwenden. Sie können Hashcodes mit vergleichen [Object:: Equals](#equals). Wenn der Codepfad äußerst wichtig ist und `GetHashCode` sowie `Equals` nicht schnell genug sind, können Sie auf die zugrunde liegende COM-Ebene herunter wechseln und systemeigene `IUnknown`-Zeigervergleiche ausführen.  
  


## <a name="gettype"></a>  Object:: GetType-Methode
Gibt eine [Platform:: Type](../cppcx/platform-type-class.md) -Objekt, das den Laufzeittyp eines Objekts beschreibt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Object::GetType()  
```  

  
### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein [Platform:: Type](../cppcx/platform-type-class.md) -Objekt, das den Laufzeittyp des Objekts beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Die statische [Type:: GetTypeCode](../cppcx/platform-type-class.md#gettypecode) dienen zum Abrufen einer [Platform:: TypeCode-Enumeration](../cppcx/platform-typecode-enumeration.md) Wert, der den aktuellen Typ darstellt. Dies ist besonders für integrierte Typen hilfreich. Der Typencode für eine Verweisklasse außer [Platform:: String](../cppcx/platform-string-class.md) ist Objekt (1).  
  
 Die [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) Klasse wird in der Windows-APIs als sprachenunabhängige Methode für Übergabe von Typinformationen zwischen Windows-Komponenten und-Apps verwendet. T[tplatform:: Type Class](../cppcx/platform-type-class.md) verfügt über Operatoren zum Konvertieren zwischen `Type` und `TypeName`.  
  
 Verwenden der [Typeid](../windows/typeid-cpp-component-extensions.md) -Operator zum Zurückgeben einer `Platform::Type` Objekt für einen Klassennamen ein, zum Beispiel beim Navigieren zwischen XAML-Seiten:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Platform:: Type-Klasse](../cppcx/platform-type-class.md)   
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)   
 [Typsystem] (.. /cppcx/Type-System-c-CX.MD
  
## <a name="ctor"></a>  Object:: Object-Konstruktor
Initialisiert eine neue Instanz der Objektklasse.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:Object()  
```  

## <a name="referenceequals"></a>  Object:: ReferenceEquals-Methode
Stellt fest, ob die angegebenen Objekt-Instanzen dieselbe Instanz sind.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2)  
```  
  
### <a name="parameters"></a>Parameter  
 obj1  
 Das erste zu vergleichende Objekt.  
  
 obj2  
 Das zweite zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die beiden Objekte identisch sind, andernfalls `false`.  
 
## <a name="tostring"></a>  Object:: ToString-Methode (C + c++ / CX)
Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:  
virtual String^ ToString()  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die das aktuelle Objekt darstellt. Sie können diese Methode überschreiben, um eine benutzerdefinierte Zeichenfolgenmeldung in der Verweisklasse oder Struktur bereitzustellen:  
  
```cpp  
public ref class Tree sealed  
{  
public:  
    Tree(){}  
    virtual Platform::String^ ToString() override  
    {  
      return "I’m a Tree";  
    };  
};  
```  
## <a name="see-also"></a>Siehe auch  
 [Platform-Namespace](platform-namespace-c-cx.md)