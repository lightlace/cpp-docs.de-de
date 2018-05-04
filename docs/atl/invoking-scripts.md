---
title: Aufrufen von Skripts (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- StringRegister
dev_langs:
- C++
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91d11b86b2b7cf17ef90ab701b06c6f31b272691
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="invoking-scripts"></a>Aufrufen von Skripts
[Mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) Ersatz Maps erläutert und die Registrierungsstelle Methode erwähnt **AddReplacement**. Die Registrierungsstelle ist acht andere spezifische Methoden des Skripts, und alle in der folgenden Tabelle beschrieben sind.  
  
|Methode|Syntaxbeschreibung /|  
|------------|-------------------------|  
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***ResFileName* **, "uint"** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Registriert das Skript in einem Modul Ressource enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. `nID` und `szType` enthalten bzw. die ID und den Typ der Ressource.|  
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***ResFileName* **, "uint"** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Hebt die Registrierung des Skripts in der Ressource eines Moduls enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. `nID` und `szType` enthalten bzw. die ID und den Typ der Ressource.|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***ResFileName* **, LPCOLESTR***SzID* **, LPCOLESTR** `szType` **);** <br /><br /> Registriert das Skript in einem Modul Ressource enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. *SzID* und `szType` enthalten bzw. Zeichenfolgenbezeichner und Typ der Ressource.|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***ResFileName* **, LPCOLESTR***SzID* **, LPCOLESTR** `szType` **);** <br /><br /> Hebt die Registrierung des Skripts in der Ressource eines Moduls enthalten sind. *ResFileName* gibt den UNC-Pfad für das Modul selbst. *SzID* und `szType` enthalten bzw. Zeichenfolgenbezeichner und Typ der Ressource.|  
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR***FileName***);** <br /><br /> Registriert das Skript in einer Datei an. *FileName* ist ein UNC-Pfad in eine Datei, die ein Ressourcenskript enthält (oder ist).|  
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR***FileName***);** <br /><br /> Hebt die Registrierung des Skripts in einer Datei. *FileName* ist ein UNC-Pfad in eine Datei, die ein Ressourcenskript enthält (oder ist).|  
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR***Daten***);** <br /><br /> Registriert das Skript in einer Zeichenfolge. *Daten* enthält das Skript selbst.|  
|**StringUnregister**|**HRESULT StringUnregister (LPCOLESTR***Daten***);** <br /><br /> Hebt die Registrierung des Skripts in einer Zeichenfolge. *Daten* enthält das Skript selbst.|  
  
 **ResourceRegisterSz** und **ResourceUnregisterSz**, ähneln **ResourceRegister** und **ResourceUnregister**, jedoch können Sie eine Zeichenfolge angeben. Der Bezeichner.  
  
 Die Methoden **FileRegister** und **FileUnregister** sind nützlich, wenn Sie nicht, dass das Skript in einer Ressource möchten oder das Skript in einer eigenen Datei verwendet werden soll. Die Methoden **StringRegister** und **StringUnregister** RGS-Datei in einem dynamisch zugewiesenen Zeichenfolge gespeichert werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

