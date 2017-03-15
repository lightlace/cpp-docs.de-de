---
title: "coclass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.coclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "coclass attribute"
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# coclass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein COM\-Objekt, das eine COM\-Schnittstelle implementieren kann.  
  
## Syntax  
  
```  
  
[coclass]  
  
```  
  
## Hinweise  
 Das Attribut **coclass** C\+\+ wird ein Co\-Klassen konstrukt in der generierten IDL\-Datei.  
  
 Wenn Sie eine Co\-Klasse definieren, können Sie [uuid](../windows/uuid-cpp-attributes.md), [Version](../windows/version-cpp.md), [Threading](../windows/threading-cpp.md), [vi\_progid](../windows/vi-progid.md)und [ProgID](../windows/progid.md)\-Attribute.  Schlägt eine von ihnen wird sie nicht angegeben wird.  
  
 Wenn zwei Headerdateien Klassen mit dem coclass\-Attribut enthalten und keine GUIDs angeben, verwendet der Compiler das gleiche GUID für beide Klassen und ergibt einen MIDL\-Fehler.  Daher sollten Sie das `uuid`\-Attribut verwenden, wenn Sie **coclass**verwenden.  
  
 **ATL\-Projekte**  
  
 Wenn dieses Attribut einer Klassen\- oder Strukturdefinition in einem ATL\-Projekt vorausgeht, es:  
  
-   Fügt Code oder Daten ein, um automatische Registrierung für das Objekt zu unterstützen.  
  
-   Fügt Code oder Daten ein, um eine COM\-Klassenfactory für das Objekt zu unterstützen.  
  
-   Fügt Code oder Daten ein, um **IUnknown** zu implementieren und das Objekt ein COM\-erstellbares Objekt auszuführen.  
  
 Dabei werden die folgenden Basisklassen für das Zielobjekt hinzugefügt:  
  
-   factory Standardklassen stellt die[CComCoClass\-Klasse](../atl/reference/ccomcoclass-class.md) Aggregations und das Modell für das Objekt bereit.  
  
-   [CComObjectRootEx\-Klasse](../atl/reference/ccomobjectrootex-class.md) verfügt über eine Vorlage auf Grundlage des Threadingmodells Klasse, die vom [Threading](../windows/threading-cpp.md)\-Attribut angegeben ist.  Wenn das **Threading**\-Attribut nicht angegeben ist, wird das standardmäßige Threadingmodell Apartment.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) wird hinzugefügt, wenn das Attribut nicht [nicht erstellbar](../windows/noncreatable.md) für das Zielobjekt angegeben wird.  
  
 Schließlich wird eine duale Schnittstelle, die nicht mit eingebetteten IDL\-Datei definiert ist, durch eine entsprechende [IDispatchImpl](../atl/reference/idispatchimpl-class.md)\-Klasse ersetzt.  Wenn die duale Schnittstelle in eingebettetem IDL\-Datei definiert ist, wird der betreffenden Schnittstelle in der Liste nicht geändert.  
  
 Das coclass\-Attribut stellt auch die folgenden Funktionen zu eingefügten Code oder im Falle `GetObjectCLSID`, als statische Methode in der Basisklasse `CComCoClass`bereit:  
  
-   `UpdateRegistry` registriert den Klassenfactorys der Zielklasse.  
  
-   `GetObjectCLSID`, die zur Registrierung verknüpft ist, kann auch verwendet werden, um die CLSID der Zielklasse zu erhalten.  
  
-   **GetObjectFriendlyName** wird standardmäßig eine Zeichenfolge im Format „\<target\-Klasse*name\>*`Object`“ zurück.  Wenn diese Funktion bereits vorhanden ist, wird es nicht hinzugefügt.  Fügen Sie diese Funktion der Zielklasse hinzu, um einen benutzerfreundlicheren Namen als automatisch generierte der zurückzugeben.  
  
-   **GetProgID**, die zur Registrierung verknüpft ist, gibt die Zeichenfolge zurück, die dem [ProgID](../windows/progid.md)\-Attribut angegeben ist.  
  
-   **GetVersionIndependentProgID** verfügt über die gleichen Funktionen wie **GetProgID**, es gibt jedoch die Zeichenfolge zurück, die [vi\_progid](../windows/vi-progid.md)angegeben wird.  
  
 Die folgenden Änderungen, die an der COM\-Zuordnung verknüpft sind, werden in der Zielklasse vorgenommen:  
  
-   Eine COM\-Zuordnung wird mit Einträgen für alle Schnittstellen hinzugefügt, die die Zielklasse von berechnet und alle Einträge durch das angegebene [COM\-Schnittstellen\-Einstiegspunkte](../mfc/com-interface-entry-points.md)\-Attribut oder die [Aggregate](../windows/aggregates.md) an, die vom Attribut erforderlich sind.  
  
-   Ein [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md) Makro in die COM\-Zuordnung eingefügt.  Dieses Makro ist vergleichbar mit [OBJECT\_ENTRY](assetId:///abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) hinsichtlich Funktionalität muss aber nicht Teil der COM\-Zuordnung der Zielklasse zu sein.  
  
 Der Name der Co\-Klasse, die in der IDL\-Datei für die Klasse generiert wird, hat den gleichen Namen wie die Klasse.  Zum Beispiel ansprechend und das folgende Beispiel, um den Klassenbezeichner für eine Co\-Klasse CMyClass, einem Client über die MIDL\-generierte Headerdatei zuzugreifen, verwenden Sie CLSID\_CMyClass.  
  
## Beispiel  
 Im folgenden Code wird gezeigt, wie das coclass\-Attribut verwendet:  
  
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
  
 Im folgenden Beispiel wird gezeigt, wie die Standardimplementierung einer Funktion überschreibt, die im Code angezeigt, der vom coclass\-Attribut eingefügt wird.  Weitere Informationen finden Sie unter [\/Fx](../build/reference/fx-merge-injected-code.md) Weitere Informationen zum Anzeigen von eingefügtem Code.  Alle Basisklassen oder Schnittstellen, die Sie für eine Klasse verwendet werden, sind im eingefügten Code.   Darüber hinaus wenn eine Klasse standardmäßig im eingefügten Code enthalten ist, und Sie diese Klasse als Basis für die Co\-Klasse angeben, verwendet der Anbieter Attribut das Formular, das in Code angegeben wird.  
  
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
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)