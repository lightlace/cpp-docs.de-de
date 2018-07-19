---
title: Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 020a7a16e38ee40c99a7a5b77c88002e3135bfa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33840917"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst
Benutzerkontensteuerung (UAC) ist eine Funktion von Windows Vista, in der Benutzerkonten eingeschränkte Berechtigungen haben. Ausführliche Informationen über UAC finden Sie auf diesen Sites:  
  
-   [Windows Vista-Konto-Steuerelement-Schritt-für-Schritt-Benutzerhandbuch](http://go.microsoft.com/fwlink/p/?linkid=53781)  
  
-   [Developer Best Practices und Richtlinien für Anwendungen in einer Umgebung mit minimalen Berechtigungen](http://go.microsoft.com/fwlink/p/?linkid=82444)  
  
-   [Verstehen und Konfigurieren der Benutzerkontensteuerung in Windows Vista](http://go.microsoft.com/fwlink/p/?linkid=82445)  
  
## <a name="building-projects-after-enabling-uac"></a>Erstellen von Projekten nach der Aktivierung von UAC  
 Wenn Sie ein Visual C++-Projekt unter Windows Vista erstellen, UAC bei der Erstellung deaktiviert ist und später aktiviert wird, müssen Sie das Projekt bereinigen und erneut erstellen, damit es ordnungsgemäß funktioniert.  
  
## <a name="applications-that-require-administrative-privileges"></a>Anwendungen, die Administratorrechte erfordern  
 Standardmäßig bettet der Visual C++-Linker ein UAC-Fragment in das Manifest einer Anwendung mit der Ausführungsebene `asInvoker` ein. Wenn die Anwendung für die ordnungsgemäße Ausführung Administratorrechte erfordert (wenn sie z. B. den HKLM-Knoten der Registrierung ändert oder in geschützte Bereiche des Datenträgers wie z. B. das Windows-Verzeichnis schreibt), müssen Sie die Anwendung ändern.  
  
 Die erste Möglichkeit besteht, so ändern Sie die UAC-Fragment des Manifests zu ändern, um die Ausführungsebene *RequireAdministrator*. Die Anwendung fordert dann den Benutzer vor der Ausführung zur Angabe von Administratorrechten auf. Informationen hierzu finden Sie unter [/MANIFESTUAC (bettet UAC-Informationen in Manifest)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Die zweite Möglichkeit besteht darin nicht UAC-Fragment in das Manifest einzubetten, durch Angeben der **/MANIFESTUAC: No** (Linkeroption). In diesem Fall wird die Anwendung virtualisiert ausgeführt. Änderungen, die Sie an der Registrierung oder am Dateisystem vornehmen, werden nach Beendigung der Anwendung nicht beibehalten.  
  
 Im folgenden Flussdiagramm wird beschrieben, wie die Anwendung abhängig davon ausgeführt wird, ob UAC aktiviert ist und ob die Anwendung ein UAC-Manifest besitzt:  
  
 ![Verhalten des Windows Vista-Ladeprogramms](media/uacflowchart.png "UACflowchart")  
  
## <a name="see-also"></a>Siehe auch  
 [Empfohlene Vorgehensweisen bezüglich der Sicherheit](security-best-practices-for-cpp.md)