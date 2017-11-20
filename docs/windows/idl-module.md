---
title: Idl_module | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.idl_module
dev_langs: C++
helpviewer_keywords: idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5d51e9344f9cebace9266c93def83fd37604ce39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="idlmodule"></a>idl_module
Gibt einen Einstiegspunkt in eine DLL-Datei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ idl_module (   
   name=module_name,   
   dllname=dll,   
   uuid="uuid",   
   helpstring="help text",   
   helpstringcontext=helpcontextID,   
   helpcontext=helpcontext,   
   hidden,   
   restricted  
) ]  
function declaration  
```  
  
#### <a name="parameters"></a>Parameter  
 **name**  
 Ein benutzerdefinierter Name für den Codeblock, der in der IDL-Datei angezeigt wird.  
  
 **DLL-Namen** (optional)  
 Die DLL-Datei, die den Export enthält.  
  
 `uuid` (optional)  
 Eine eindeutige ID.  
  
 **Helpstring** (optional)  
 Eine Zeichenfolge, die zum Beschreiben der Typbibliothek.  
  
 **helpstringcontext** (optional)  
 Die ID eines Hilfethemas in einer HLP oder CHM-Datei.  
  
 **helpcontext** (optional)  
 Die Hilfe-ID für diese Typbibliothek.  
  
 **hidden** (optional)  
 Parameter, der verhindert, dass die Bibliothek angezeigt wird. Weitere Informationen finden Sie unter [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL-Attribut.  
  
 ***Eingeschränkte*** (optional)  
 Mitglieder der Bibliothek können nicht nach dem Zufallsprinzip aufgerufen werden. Weitere Informationen finden Sie unter [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL-Attribut.  
  
 *Funktionsdeklaration*  
 Die Funktion, die Sie definieren.  
  
## <a name="remarks"></a>Hinweise  
 Die `idl_module` C++-Attribut ermöglicht die Angabe den Einstiegspunkt in eine DLL-Datei aus einer DLL-Datei importieren können.  
  
 Die **Idl_module** Attribut hat ähnliche Funktionen der [Modul](http://msdn.microsoft.com/library/windows/desktop/aa367099) MIDL-Attribut.  
  
 Sie können etwas von einem COM-Objekt exportieren, die Sie aus einer DLL-Datei exportieren können, indem Sie einen DLL-Einstiegspunkt in den bibliotheksblock einer IDL-Datei einfügen.  
  
 Ihre Striches `idl_module` in zwei Schritten. Zunächst müssen Sie ein Paar von Namen/DLL definieren. Klicken Sie dann bei Verwendung von `idl_module` um einen Einstiegspunkt anzugeben, geben Sie den Namen und zusätzliche Attribute.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie die `idl_module` Attribut:  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
 [entry](../windows/entry.md)   
