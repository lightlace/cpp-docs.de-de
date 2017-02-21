---
title: "Invoking Scripts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StringRegister"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Skripts, invoking registry in ATL"
  - "StringRegister method"
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Invoking Scripts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Verwenden von ersetzbaren Parameter \(der Präprozessor der Registrierungsstelle\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) erläutert Ersatzzuordnungen und erwähnt die Registrierungsstellenmethode **AddReplacement**.  Die Registrierungsstelle hat acht andere Methoden, die dem Skripterstellung spezifisch sind, und alle werden in der folgenden Tabelle beschrieben.  
  
|Methode|Syntax\/Beschreibung|  
|-------------|--------------------------|  
|**ResourceRegister**|**HRESULT ResourceRegister\( LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType`\);<br /><br /> Registriert das Skript, das in der Ressource eines Moduls enthalten ist.  *resFileName* gibt den UNC\-Pfad des Modul selbst an.  `nID` und `szType` enthalten die ID und den Typ der Ressource, bzw.|  
|**ResourceUnregister**|**HRESULT ResourceUnregister\( LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType`\);<br /><br /> Hebt das Skript Registrierung in der Ressource eines Moduls enthalten ist.  *resFileName* gibt den UNC\-Pfad des Modul selbst an.  `nID` und `szType` enthalten die ID und den Typ der Ressource, bzw.|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz\( LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType`\);<br /><br /> Registriert das Skript, das in der Ressource eines Moduls enthalten ist.  *resFileName* gibt den UNC\-Pfad des Modul selbst an.  *szID* und `szType` enthalten den Zeichenfolgenbezeichner und \- typ der Ressource, bzw.|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz\( LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType`\);<br /><br /> Hebt das Skript Registrierung in der Ressource eines Moduls enthalten ist.  *resFileName* gibt den UNC\-Pfad des Modul selbst an.  *szID* und `szType` enthalten den Zeichenfolgenbezeichner und \- typ der Ressource, bzw.|  
|**FileRegister**|**HRESULT FileRegister\( LPCOLESTR**  *Dateiname* \);<br /><br /> Registriert das Skript in einer Datei.  *Dateiname*  ist ein UNC\-Pfad zu einer Datei, die \(oder\) ist ein Ressourcenskript enthält.|  
|**FileUnregister**|**HRESULT FileUnregister\( LPCOLESTR**  *Dateiname* \);<br /><br /> Hebt das Skript in einer Datei Registrierung auf.  *Dateiname*  ist ein UNC\-Pfad zu einer Datei, die \(oder\) ist ein Ressourcenskript enthält.|  
|**StringRegister**|**HRESULT StringRegister\( LPCOLESTR**  *Daten* \);<br /><br /> Registriert das Skript in eine Zeichenfolge.  *Daten*  enthalten das Skript selbst.|  
|**StringUnregister**|**HRESULT StringUnregister\( LPCOLESTR**  *Daten* \);<br /><br /> Hebt das Skript in einer Zeichenfolge Registrierung auf.  *Daten*  enthalten das Skript selbst.|  
  
 **ResourceRegisterSz** und **ResourceUnregisterSz**, sind für **ResourceRegister** und zu **ResourceUnregister** ähnlich, aber es Ihnen ermöglicht, einen Zeichenfolgenbezeichner anzugeben.  
  
 Die Methoden **FileRegister** und **FileUnregister** sind nützlich, wenn Sie nicht das Skript in einer Ressource verwenden möchten, oder wenn Sie das Skript in einer eigenen Datei soll.  Die Methoden **StringRegister** und **StringUnregister** ermöglichen die in einer dynamisch zugeordneten Zeichenfolge gespeichert werden RGS\-Datei.  
  
## Siehe auch  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)