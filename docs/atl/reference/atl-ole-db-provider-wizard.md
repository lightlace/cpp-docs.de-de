---
title: ATL-OLE DB-Anbieter-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.provider.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL OLE DB Provider Wizard
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a28a47d9af89470c63903ccc338c680361b1cada
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="atl-ole-db-provider-wizard"></a>ATL-OLE DB-Anbieter-Assistent
Dieser Assistent erstellt die Klassen, die einen OLE DB-Anbieter zu erstellen.  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], die von diesem Assistenten erstellte Registrierungsskript registriert die COM-Komponenten unter **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **Register-Komponente für alle Benutzer** des ATL-Assistenten die Option.  
  
 Die folgende Tabelle beschreibt die Optionen für die ATL-OLE DB-Anbieter-Assistenten:  
  
 **Kurzname**  
 Geben Sie den kurzen Namen des Anbieters erstellt werden soll. Die anderen Bearbeitungsfelder, die Sie im Assistenten werden automatisch aufgefüllt werden basierend auf den Sie hier eingeben. Wenn Sie möchten, können Sie die anderen Namensfelder bearbeiten.  
  
 **Co-Klasse**  
 Der Name der Co-Klasse. Die ProgID Name ändert sich entsprechend diesem Namen.  
  
 **Mit Attributen versehen**  
 Diese Option gibt an, ob der Assistent mithilfe von Attributen oder Vorlagendeklarationen-Anbieterklassen erstellt wird. Wenn Sie diese Option auswählen, verwendet der Assistent Attribute anstelle von Vorlagendeklarationen (Dies ist die Standardoption, wenn Sie ein attributiertes Projekt erstellt haben). Wenn Sie diese Option deaktivieren, verwendet der Assistent Vorlagendeklarationen anstelle von Attributen (Dies ist die Standardoption, wenn Sie ein nicht attributiertes Projekt erstellt haben).  
  
 Wenn Sie diese Option auswählen, wenn Sie ein Projekt nicht attributierte erstellt haben, warnt Sie der Assistent, dass das Projekt in ein attributiertes Projekt konvertiert wird und Sie, ob fortzusetzen fragt, oder nicht.  
  
 **ProgID**  
 Die ProgID oder den programmatischen Bezeichner ist eine Textzeichenfolge, die Ihre Anwendung, anstatt eine GUID verwenden können. Die ProgID Name weist folgendes Format *Projectname.Coclassname*.  
  
 **Version**  
 Die Versionsnummer des Anbieters. Der Standard ist 1.  
  
 **DataSource-Klasse**  
 Der Name der Quellklasse Daten des Formulars C*Shortname*Quelle.  
  
 **DataSource .h-Datei**  
 Die Headerdatei für die Data Source-Klasse. Sie können der Name dieser Datei bearbeiten, oder wählen eine bestehende Headerdatei.  
  
 **Session-Klasse**  
 Der Name der Sitzungsklasse des Formulars C*Shortname*Sitzung.  
  
 **Sitzung .h-Datei**  
 Die Headerdatei für die Sitzungsklasse. Sie können der Name dieser Datei bearbeiten, oder wählen eine bestehende Headerdatei.  
  
 **Command-Klasse**  
 Der Name des Command-Klasse, im Format C*Shortname*Befehl.  
  
 **Befehl .h-Datei**  
 Die Headerdatei für das Command-Klasse. Dieser Name kann nicht bearbeitet werden und richtet sich nach den Namen der Rowset-Headerdatei.  
  
 **Rowset-Klasse**  
 Der Name der Rowsetklasse des Formulars C*Shortname*Rowset.  
  
 **Rowset .h-Datei**  
 Die Headerdatei für die Rowsetklasse. Sie können der Name dieser Datei bearbeiten, oder wählen eine bestehende Headerdatei.  
  
 **Rowset-cpp-Datei**  
 Der Anbieter Implementierungsdatei einschließen. Sie können der Name dieser Datei bearbeiten oder eine vorhandene Implementierungsdatei auswählen.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-OLE DB-Anbieter](../../atl/reference/adding-an-atl-ole-db-provider.md)


