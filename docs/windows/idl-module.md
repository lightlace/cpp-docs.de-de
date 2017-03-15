---
title: "idl_module | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.idl_module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_module attribute"
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# idl_module
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt einen Einstiegspunkt in einer DLL\-Datei an.  
  
## Syntax  
  
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
  
#### Parameter  
 **Name**  
 Ein benutzerdefinierter Name für den Codeblock, der in der IDL\-Datei angezeigt wird.  
  
 **dllname** \(optional\)  
 Die DLL\-Datei, die den Export enthält.  
  
 `uuid` \(optional\)  
 Eine eindeutige ID.  
  
 **helpstring** \(optional\)  
 Eine Zeichenfolge, die die Typbibliothek zu beschreiben.  
  
 **helpstringcontext** \(optional\)  
 Die ID des Hilfethemas in einem .hlp oder CHM\-Datei.  
  
 **helpcontext** \(optional\)  
 Die Hilfe ID für diese Typbibliothek.  
  
 **hidden** \(optional\)  
 Ein Parameter, der verhindert, dass die Bibliothek angezeigt.  Weitere Informationen finden Sie im [Hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL\-Attribut.  
  
 ***restricted***  \(optional\)  
 Mitglieder der Bibliothek können nicht willkürlich aufgerufen werden.  Weitere Informationen finden Sie im [Einschränkung](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL\-Attribut.  
  
 *Funktionsdeklaration*  
 Die Funktion, die Sie definieren.  
  
## Hinweise  
 Das Attribut `idl_module` C\+\+ können Sie den Einstiegspunkt in einer DLL\-Datei angeben, die Sie zum Import aus einer DLL\-Datei zulässig.  
  
 Das **idl\_module** Attribut verfügt die Funktionalität zum [Modul](http://msdn.microsoft.com/library/windows/desktop/aa367099) MIDL\-Attribut ähnelt.  
  
 Sie können alle von einem COM\-Objekt, das Exportieren aus einer DLL exportieren können, indem Sie einen DLL\-Einstiegspunkt in einer IDL\-Datei Library\-Block ablegen.  
  
 Die Muss\-Verwendung `idl_module` in zwei Schritten.  Zuerst müssen Sie ein paar name\-\/DLL definieren.  Wenn Sie anschließend `idl_module` verwenden, um einen Einstiegspunkt angeben möchten, geben Sie den Namen und die alle zusätzlichen Attribute an.  
  
## Beispiel  
 Im folgenden Code wird gezeigt, wie das `idl_module`\-Attribut verwendet:  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [entry](../windows/entry.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)