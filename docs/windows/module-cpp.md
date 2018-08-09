---
title: Modul (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.module
dev_langs:
- C++
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e7354dc422027207bc1dab357487ffcce48a4ca
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018593"
---
# <a name="module-c"></a>module (C++)
Definiert den Bibliotheksblock in der IDL-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[ module (  
   type=dll,  
   name=string,  
   version=1.0,  
   uuid=uuid,  
   lcid=integer,  
   control=boolean,  
   helpstring=string,  
   helpstringdll=string,  
   helpfile=string,  
   helpcontext=integer,  
   helpstringcontext=integer,  
   hidden=boolean,  
   restricted=boolean,  
   custom=string,  
   resource_name=string,  
) ];  
```  
  
### <a name="parameters"></a>Parameter  
*Typ* (optional)  
Einer der folgenden Werte ist möglich:  
  
-   `dll` Fügt Funktionen und Klassen, mit die die resultierende DLL als in-Process-com-Server verwendet werden können. Dies ist der Standardwert.  
  
-   `exe` Fügt Funktionen und Klassen, mit denen die resultierende ausführbare Datei als ein Out-of-Process-COM-Server-Funktion.  
  
-   `service` Fügt Funktionen und Klassen, mit denen die resultierende ausführbare Datei als ein NT-Dienst zu.  
  
-   `unspecified` Deaktiviert die Einfügung von ATL-Code im Zusammenhang mit dem Modulattribut: Einfügung der ATL-Modulklasse, globalen Instanz _AtlModule und von Einstiegspunkt zeigen Funktionen. Einfügen von ATL-Code aufgrund von anderen Attributen im Projekt wird nicht deaktiviert.  
  
*name* (optional)  
Der Name des Bibliotheksblocks.  
  
*Version* (optional)  
Die Versionsnummer, die Sie dem Bibliotheksblock zuweisen möchten. Der Standardwert ist 1,0.  
  
*uuid*  
Eindeutige ID für die Bibliothek. Wenn Sie diesen Parameter weglassen, wird automatisch eine ID für die Bibliothek generiert. Müssen Sie möglicherweise Abrufen der *Uuid* des Blocks Bibliothek, die Sie mithilfe des Bezeichners können **__uuidof (***Libraryname***)**.  
  
*lcid*  
Der Lokalisierungsparameter. Weitere Informationen finden Sie unter [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) .  
  
*Steuerelement* (optional)  
Gibt an, dass alle Co-Klassen in der Bibliothek Steuerelemente sind.  
  
*helpstring*  
Gibt die Typbibliothek an.  
  
*Helpstringdll* (optional)  
Gibt den Namen der DLL-Datei zum Ausführen der Suche nach einem Dokument an. Weitere Informationen finden Sie unter [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) .  
  
*HelpFile* (optional)  
Der Name des der **Hilfe** -Datei für die Typbibliothek.  
  
*HelpContext* (optional)  
Die **Hilfe-ID** für diese Typbibliothek.  
  
*Helpstringcontext* (optional)  
Weitere Informationen finden Sie unter [helpstringcontext](../windows/helpstringcontext.md) .  
  
*Ausgeblendete* (optional)  
Verhindert, dass die gesamte Bibliothek angezeigt wird. Dies ist für die Verwendung mit Steuerelementen vorgesehen. Hosts müssen eine neue Typbibliothek erstellen, die das Steuerelement mit erweiterten Eigenschaften umschließt. Weitere Informationen finden Sie unter [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL-Attribut.  
  
*Eingeschränkte* (optional)  
Mitglieder der Bibliothek können nicht willkürlich aufgerufen werden. Weitere Informationen finden Sie unter [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL-Attribut.  
  
*benutzerdefinierte* (optional)  
Ein oder mehrere Attribute; dies ist vergleichbar mit dem [custom](../windows/custom-cpp.md) -Attribut. Der erste Parameter für *benutzerdefinierte* ist die GUID des Attributs. Zum Beispiel:  
  
```  
[module(custom={guid,1}, custom={guid1,2})]  
```  
  
*resource_name*  
Die Zeichenfolgenressource-ID der RGS-Datei, die verwendet wird, um die APP-ID der DLL, ausführbaren Datei oder des Diensts zu registrieren. Wenn das Modul vom Typ Dienst ist, wird dieses Argument auch verwendet, um die ID der Zeichenfolge mit dem Dienstnamen zu erhalten.  
  
> [!NOTE]
>  Die RGS-Datei und die Zeichenfolge, die den Namen des Diensts enthält, sollten den gleichen numerischen Wert enthalten.  
  
## <a name="remarks"></a>Hinweise  
 Es sei denn, Sie geben die *eingeschränkten* Parameter, um [Emitidl](../windows/emitidl.md), **Modul** muss in jedem Programm, das C++-Attribute verwendet.  
  
 Ein Bibliotheksblock wird erstellt, wenn Sie zusätzlich zum **module** -Attribut im Quellcode auch [dispinterface](../windows/dispinterface.md), [dual](../windows/dual.md), [object](../windows/object-cpp.md)oder ein Attribut, das [coclass](../windows/coclass.md)impliziert, verwenden.  
  
 Pro IDL-Datei ist ein Bibliotheksblock zulässig. Mehrere Modul-Einträge im Quellcode werden zusammengeführt und die neuesten Parameterwerte werden implementiert.  
  
 Wenn dieses Attribut in einem Projekt verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs. Zusätzlich zu den oben beschriebenen Verhalten fügt das Attribut auch ein globales Objekt (namens `_AtlModule`) mit den korrekten Typ und Code für zusätzliche Unterstützung. Wenn das Attribut eigenständig ist, wird eine von dem richtigen Modultyp abgeleitete Klasse eingefügt. Wenn das Attribut auf eine Klasse angewendet wird, wird eine Basisklasse des richtigen Modultyps hinzugefügt. Der richtige Typ wird durch den Wert bestimmt die *Typ* Parameter:  
  
-   `type` = **dll**  
  
     [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) dient als Basisklasse und als für einen COM-Server erforderliche Standard-DLL-Einstiegspunkte. Diese Einstiegspunkte sind [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583), [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162), [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368)und [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891).  
  
-   `type` = **exe**  
  
     [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) dient als Basisklasse und ausführbarer Standardeinstiegspunkt [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` = **service**  
  
     [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) dient als Basisklasse und ausführbarer Standardeinstiegspunkt [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` = **unspecified**  
  
     Deaktiviert die Einfügung von ATL-Code im Zusammenhang mit dem Modulattribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie ein Bibliotheksblock in der generierten IDL-Datei erstellt wird.  
  
```cpp  
// cpp_attr_ref_module1.cpp  
// compile with: /LD  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
```  
  
 Der folgende Code zeigt, dass Sie Ihre eigene Implementierung einer Funktion angeben können, die in dem Code angezeigt wird, der durch die Verwendung von **module**eingefügt wurde. Weitere Informationen zum Anzeigen von eingefügtem Code finden Sie unter [/Fx](../build/reference/fx-merge-injected-code.md) . Um eine der Funktionen zu überschreiben, die vom Attribut **module** eingefügt wurden, erstellen Sie eine Klasse, die die Implementierung der Funktion enthält, und wenden Sie das Attribut **module** auf diese Klasse an.  
  
```cpp  
// cpp_attr_ref_module2.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// no semicolon after attribute block  
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [usesgetlasterror](../windows/usesgetlasterror.md)   
 [Bibliothek](http://msdn.microsoft.com/library/windows/desktop/aa367069)   
 [HelpContext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
 [HelpFile](../windows/helpfile.md)   
 [version](../windows/version-cpp.md)   