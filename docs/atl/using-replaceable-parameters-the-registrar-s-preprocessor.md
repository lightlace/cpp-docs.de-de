---
title: Mithilfe von ersetzbaren Parametern (ATL-Registrierung) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AddReplacement
- ClearReplacements
dev_langs: C++
helpviewer_keywords: '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b06333ba51b74501f3b7cd68248e5fb7e51ca94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Mithilfe von ersetzbaren Parametern (die Registrierungsstelle &#39; s Präprozessor)
Ersetzbare Parameter ermöglichen einer Registrierungsstelle Client zur Laufzeit Daten anzugeben. Zu diesem Zweck verwaltet die Registrierungsstelle eine Ersatz-Zuordnung in die er die Werte der ersetzbare Parameter in Ihrem Skript zugeordnet wird. Die Registrierungsstelle stellt diese Einträge zur Laufzeit.  
  
##  <a name="_atl_using_.25.module.25"></a>Mithilfe von "%-Modul"  
 Die [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md) generiert automatisch ein Skript, das verwendet `%MODULE%`. ATL verwendet diesen ersetzbaren Parameter für den tatsächlichen Speicherort der DLL oder EXE-Datei des Servers an.  
  
## <a name="concatenating-run-time-data-with-script-data"></a>Verketten von Laufzeitdaten mit Skriptdaten  
 Eine weitere Verwendungsmöglichkeit der der Präprozessor ist Laufzeitdaten mit Skriptdaten verketten. Nehmen wir beispielsweise an, die ein Eintrag ist erforderlich, die einen vollständigen Pfad zu einem Modul mit der Zeichenfolge enthält "`, 1`" am Ende angefügt. Zuerst definieren Sie die Erweiterung die folgenden:  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 Klicken Sie dann vor dem Aufrufen einer der das Skript aufgeführten Methoden verarbeiten [Skripts aufrufen](../atl/invoking-scripts.md), Ersatz zur Zuordnung hinzufügen:  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 Beim Analysieren des Skripts, die Registrierungsstelle erweitert `'%MODULE%, 1'` auf `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  In einem Skript Registrierungsstelle beträgt 4 KB maximale Tokengröße. (Ein Token ist jedes erkennbare Element in der Syntax.) Dies schließt ein Token, die erstellt oder vom Präprozessor erweitert wurden.  
  
> [!NOTE]
>  Um Ersatzwerte zur Laufzeit ersetzen möchten, entfernen Sie den Aufruf in das Skript, um die [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) oder [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) Makro. Ersetzen Sie es stattdessen mit Ihren eigenen `UpdateRegistry` -Methode, die Aufrufe [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources), und übergeben Sie das Array von **_ATL_REGMAP_ENTRY** Strukturen. Das Array von **_ATL_REGMAP_ENTRY** benötigen Sie mindestens einen Eintrag, der festgelegt wird, um {**NULL**,**NULL**}, und diesen Eintrag sollte immer der letzte Eintrag sein. Andernfalls kann auf einem Zugriffsverletzungsfehler werden generiert, wenn **UpdateRegistryFromResource** aufgerufen wird.  
  
> [!NOTE]
>  Beim Erstellen eines Projekts, die eine ausführbare Datei ausgibt, fügt ATL automatisch Anführungszeichen um den Pfadnamen erstellt zur Laufzeit mit der **-Modul %** Registrierungsstelle Skriptparameter. Wenn Sie nicht den Pfadnamen an, die Anführungszeichen ebenfalls angeben möchten, verwenden Sie die neue **%MODULE_RAW%** Parameter stattdessen.  
>   
>  Wenn ein Projekt erstellen, eine DLL ausgibt, ATL wird nicht hinzufügen, Anführungszeichen der Pfadname Wenn **-Modul %** oder **%MODULE_RAW%** verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

