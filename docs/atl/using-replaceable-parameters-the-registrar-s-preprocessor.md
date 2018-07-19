---
title: Verwenden von ersetzbaren Parametern (ATL-Registrierung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AddReplacement
- ClearReplacements
dev_langs:
- C++
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd07a96feae192bd2235b5621da6fe42666280bd
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849496"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Verwenden von ersetzbaren Parametern (die Registrierungsstelle&#39;s Präprozessor)
Ersetzbare Parameter ermöglichen eine Registrierungsstelle Client Laufzeitdaten angeben. Zu diesem Zweck verwaltet die Registrierungsstelle eine Ersatz-Zuordnung, die in das die ersetzbaren Parametern in Ihrem Skript zugeordneten Werte wechselt Sie in. Die Registrierungsstelle wird diese Einträge zur Laufzeit.  
  
##  <a name="_atl_using_.25.module.25"></a> Verwenden %-Modul  
 Die [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md) generiert automatisch ein Skript, das verwendet `%MODULE%`. ATL verwendet diesen ersetzbaren Parameter für den tatsächlichen Speicherort der DLL oder EXE-Datei Ihres Servers.  
  
## <a name="concatenating-run-time-data-with-script-data"></a>Verketten von Laufzeitdaten mit Skriptdaten  
 Eine weitere Verwendungsmöglichkeit der Präprozessor ist zur Laufzeit Daten mit Skriptdaten verketten. Nehmen wir beispielsweise an, die ein Eintrag ist erforderlich, die einen vollständigen Pfad zu einem Modul mit der Zeichenfolge enthält "`, 1`" am Ende angefügt. Definieren Sie zuerst die folgenden Erweiterungen:  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 Klicken Sie dann vor dem Aufrufen eines der aufgeführten Methoden für die skriptverarbeitung [Aufrufen von Skripts](../atl/invoking-scripts.md), Ersatz der Zuordnung hinzuzufügen:  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 Während der Analyse des Skripts, die Registrierungsstelle erweitert `'%MODULE%, 1'` zu `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  In einem Skript Registrierungsstelle beträgt 4 KB für die maximale Größe des Tokens. (Ein Token ist erkennbare Element in der Syntax.) Dies schließt die Token, die erstellt oder vom Präprozessor erweitert wurden.  
  
> [!NOTE]
>  Um Ersatzwerte zur Laufzeit zu ersetzen, entfernen Sie den Aufruf in das Skript die [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) oder [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) Makro. Ersetzen Sie ihn stattdessen durch Ihre eigenen `UpdateRegistry` -Methode, die Aufrufe [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources), und übergeben Sie Ihr Array mit _ATL_REGMAP_ Eintrag-Strukturen. Das Array von _ATL_REGMAP_ENTRY müssen mindestens einen Eintrag, der auf {NULL, NULL} festgelegt ist, und diesen Eintrag sollte immer der letzte Eintrag sein. Andernfalls kann ein Zugriffsverletzungsfehler werden generiert, wenn `UpdateRegistryFromResource` aufgerufen wird.  
  
> [!NOTE]
>  Beim Erstellen eines Projekts, der eine ausführbare Datei ausgibt, fügt ATL automatisch Anführungszeichen um den Pfadnamen erstellt zur Laufzeit mit der **Modul %** Registrierungsstelle Script-Parameter. Wenn Sie nicht über den Pfadnamen an, die Anführungszeichen ebenfalls angeben möchten, verwenden Sie die neue **%MODULE_RAW%** Parameter stattdessen.  
>   
>  Beim Erstellen eines Projekts, das eine DLL-Datei ausgibt, ATL wird nicht hinzufügen, Anführungszeichen im Pfadnamen Wenn **Modul %** oder **%MODULE_RAW%** verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

