---
title: Aufrufen von Skripts (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StringRegister
dev_langs: C++
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cbf969f601bd90e84bf0ee15ae2ea3dcb392610
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="invoking-scripts"></a>Aufrufen von Skripts
[Mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) Ersatz Maps erläutert und die Registrierungsstelle Methode erwähnt **AddReplacement**. Die Registrierungsstelle ist acht andere spezifische Methoden des Skripts, und alle in der folgenden Tabelle beschrieben sind.  
  
|Methode|Syntaxbeschreibung /|  
|------------|-------------------------|  
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***ResFileName* **, "uint"** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Registriert das Skript in einem Modul Ressource enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. `nID`und `szType` enthalten bzw. die ID und den Typ der Ressource.|  
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***ResFileName* **, "uint"** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Hebt die Registrierung des Skripts in der Ressource eines Moduls enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. `nID`und `szType` enthalten bzw. die ID und den Typ der Ressource.|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***ResFileName* **, LPCOLESTR***SzID* **, LPCOLESTR** `szType` **);** <br /><br /> Registriert das Skript in einem Modul Ressource enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. *SzID* und `szType` enthalten bzw. Zeichenfolgenbezeichner und Typ der Ressource.|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***ResFileName* **, LPCOLESTR***SzID* **, LPCOLESTR** `szType` **);** <br /><br /> Hebt die Registrierung des Skripts in der Ressource eines Moduls enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. *SzID* und `szType` enthalten bzw. Zeichenfolgenbezeichner und Typ der Ressource.|  
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR***FileName***);** <br /><br /> Registriert das Skript in einer Datei an. *FileName* ist ein UNC-Pfad in eine Datei, die ein Ressourcenskript enthält (oder ist).|  
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR***FileName***);** <br /><br /> Hebt die Registrierung des Skripts in einer Datei. *FileName* ist ein UNC-Pfad in eine Datei, die ein Ressourcenskript enthält (oder ist).|  
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR***Daten***);** <br /><br /> Registriert das Skript in einer Zeichenfolge. *Daten* enthält das Skript selbst.|  
|**StringUnregister**|**HRESULT StringUnregister (LPCOLESTR***Daten***);** <br /><br /> Hebt die Registrierung des Skripts in einer Zeichenfolge. *Daten* enthält das Skript selbst.|  
  
 **ResourceRegisterSz** und **ResourceUnregisterSz**, ähneln **ResourceRegister** und **ResourceUnregister**, können Sie angeben, aber ein Zeichenfolgenbezeichner.  
  
 Die Methoden **FileRegister** und **FileUnregister** sind nützlich, wenn Sie nicht, dass das Skript in einer Ressource möchten oder das Skript in einer eigenen Datei verwendet werden soll. Die Methoden **StringRegister** und **StringUnregister** RGS-Datei in einem dynamisch zugewiesenen Zeichenfolge gespeichert werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

