---
title: Co-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.coclass
dev_langs:
- C++
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bcae762c603f05ce11eae5d14eb2e182c666797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coclass"></a>coclass
Erstellt ein COM-Objekt, die eine COM-Schnittstelle implementieren können.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[coclass]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Coclass** C++-Attribut ein Konstrukt Co-Klasse in der generierten IDL-Datei platziert.  
  
 Wenn Sie eine Co-Klasse zu definieren, können Sie auch angeben der [Uuid](../windows/uuid-cpp-attributes.md), [Version](../windows/version-cpp.md), [threading](../windows/threading-cpp.md), [Vi_progid](../windows/vi-progid.md), und [progid ](../windows/progid.md) Attribute. Wenn eines dieser nicht angegeben ist, wird er erstellt werden.  
  
 Enthält zwei Headerdateien Klassen mit der **Coclass** Attribut, und geben Sie an einer GUID, die der Compiler verwendet den gleiche GUID für beide Klassen und werden. Dies führt zu einem Fehler "MIDL".  Daher sollten Sie verwenden die `uuid` -Attribut bei der Verwendung **Coclass**.  
  
 **ATL-Projekte**  
  
 Wenn dieses Attribut in einem ATL-Projekt, vor die Definition einer Klasse oder Struktur steht es:  
  
-   Fügen Code oder Daten zur Unterstützung der automatischen Registrierung für das Objekt.  
  
-   Fügt Code- oder Datenmenge um ein COM-Klassenfactory für das Objekt zu unterstützen.  
  
-   Fügt Code- oder Datenmenge implementieren **IUnknown** , und stellen Sie dem Objekt ein COM-erstellbares Objekt.  
  
 Insbesondere werden die folgenden Basisklassen auf das Zielobjekt hinzugefügt:  
  
-   [CComCoClass Klasse](../atl/reference/ccomcoclass-class.md) die Factory und Aggregation Standardmodell von Klasse für das Objekt enthält.  
  
-   [CComObjectRootEx Klasse](../atl/reference/ccomobjectrootex-class.md) verfügt über eine Vorlage basierend auf der threading Modellklasse gemäß der [threading](../windows/threading-cpp.md) Attribut. Wenn die **threading** Attribut ist nicht angegeben wird, die Standardeinstellung Threadingmodell Apartment.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) wird hinzugefügt, wenn die [Noncreatable](../windows/noncreatable.md) Attribut wurde nicht für das Zielobjekt angegeben.  
  
 Zum Schluss wird eine duale Schnittstelle, die nicht mit eingebetteten IDL definiert ist mit dem entsprechenden ersetzt [IDispatchImpl](../atl/reference/idispatchimpl-class.md) Klasse. Wenn die duale Schnittstelle in der eingebetteten IDL definiert ist, wird die Schnittstelle in der Basisliste nicht geändert werden.  
  
 Die **Coclass** Attribut auch stellt die folgenden Funktionen zur Verfügung über eingefügten Code oder in der Groß-/Kleinschreibung `GetObjectCLSID`, als statische Methode in der Basisklasse `CComCoClass`:  
  
-   `UpdateRegistry`registriert die Klassenfactorys der Zielklasse an.  
  
-   `GetObjectCLSID`, die mit der Registrierung, verknüpft ist kann auch zum Abrufen der CLSID der Zielklasse verwendet werden.  
  
-   **GetObjectFriendlyName** Standardmäßig gibt eine Zeichenfolge im Format "\<*Name der Zielklasse*> `Object`". Wenn diese Funktion bereits vorhanden ist, wird er nicht hinzugefügt. Fügen Sie diese Funktion der Zielklasse zurückzugebenden einen benutzerfreundlicheren Namen als die automatisch generiert.  
  
-   **GetProgID**, bezieht sich auf die Registrierung, gibt die Zeichenfolge angegeben, mit der [progid](../windows/progid.md) Attribut.  
  
-   **GetVersionIndependentProgID** hat die gleiche Funktion wie **GetProgID**, jedoch wird die Zeichenfolge, die mit angegebenen [Vi_progid](../windows/vi-progid.md).  
  
 Die folgenden Änderungen, die die COM-Zuordnung miteinander verbunden sind, werden an die Zielklasse vorgenommen:  
  
-   Eine COM-Zuordnung wird hinzugefügt, und für alle Schnittstellen abgeleitet von der Zielklasse und alle Einträge, die gemäß der [Einstiegspunkte für COM-Schnittstellen](../mfc/com-interface-entry-points.md) Attribut oder denen der [Aggregate](../windows/aggregates.md) Attribut.  
  
-   Ein [OBJECT_ENTRY_AUTO](../atl/reference/object-map-macros.md#object_entry_auto) Makro wird in der COM-Zuordnung eingefügt.
  
 Der Name der Co-Klasse, die in der IDL-Datei für die Klasse generierte müssen den gleichen Namen wie die Klasse.  Verwenden Sie z. B. und verweisen auf die im folgenden Beispiel wird für den Zugriff auf die Klassen-ID für einen Co-Klasse CMyClass, in einem Client über die MIDL-generierten Headerdatei CLSID_CMyClass aus.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie die **Coclass** Attribut:  
  
```  
// cpp_attr_ref_coclass1.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),   
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]  
class CMyClass : public I {};  
```  
  
 Im folgende Beispiel wird gezeigt, wie die standardmäßige Implementierung einer Funktion zu überschreiben, die in den vom eingefügten Code angezeigt wird der **Coclass** Attribut. Weitere Informationen zum Anzeigen von eingefügtem Code finden Sie unter [/Fx](../build/reference/fx-merge-injected-code.md) . Alle Basisklassen oder Schnittstellen, mit denen Sie für eine Klasse wird werden in den eingefügten Code angezeigt.   Darüber hinaus wird, wenn eine Klasse ist standardmäßig in den eingefügten Code enthalten, und Sie explizit dieser Klasse als Basis für die Co-Klasse angeben, die Attributanbieter das Formular im Code angegeben verwenden.  
  
```  
// cpp_attr_ref_coclass2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface bb {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class CMyClass : public bb {  
public:  
   // by adding the definition of UpdateRegistry to your code,   
   // the function will not be included in the injected code  
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {  
      // you can add to the default implementation  
      CRegistryVirtualMachine rvm;  
      HRESULT hr;  
      if (FAILED(hr = rvm.AddStandardReplacements()))  
         return hr;  
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());  
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),  
         GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);  
   }  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [COM-Attribute](../windows/com-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)