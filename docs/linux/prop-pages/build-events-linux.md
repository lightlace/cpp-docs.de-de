---
title: Remotebuildereignisse (Linux C++) | Microsoft Docs
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165d3690-5bd8-4b0b-bc66-8b699d85a61b
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.Description
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 951b383708740aa4cd7571afc007f6fb328c254c
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="build-event-properties-linux-c"></a>Buildereigniseigenschaften (Linux C++) 


## <a name="pre-build-event"></a>Präbuildereignis
Eigenschaft | Beschreibung
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auszuführende Präbuildereignis-Tool an.
Beschreibung | Gibt eine Beschreibung für das anzuzeigende Präbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.

## <a name="pre-link-event"></a>Prälinkereignis
Eigenschaft | Beschreibung
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auszuführende Prälinkereignis-Tool an.
Beschreibung | Gibt eine Beschreibung für das anzuzeigende Prälinkereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.

## <a name="post-build-event"></a>Postbuildereignis
Eigenschaft | Beschreibung
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auszuführende Postbuildereignis-Tool an.
Beschreibung | Gibt eine Beschreibung für das anzuzeigende Postbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.

## <a name="remote-pre-build-event"></a>Remote-Präbuildereignis
Eigenschaft | Beschreibung
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auf dem Remotesystem auszuführende Präbuildereignis-Tool an.
Beschreibung | Gibt eine Beschreibung für das anzuzeigende Präbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die vom Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen remote und lokal mit der folgenden Syntax bereitgestellt werden: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2. Dabei kann eine Remotedatei an den angegebenen Speicherort auf dem lokalen Computer kopiert werden.

## <a name="remote-pre-link-event"></a>Remote-Prälinkereignis
Eigenschaft | Beschreibung
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auf dem Remotesystem auszuführende Prälinkereignis-Tool an.
Beschreibung | Gibt eine Beschreibung für das anzuzeigende Prälinkereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die vom Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen remote und lokal mit der folgenden Syntax bereitgestellt werden: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2. Dabei kann eine Remotedatei an den angegebenen Speicherort auf dem lokalen Computer kopiert werden.

## <a name="remote-post-build-event"></a>Remote-Postbuildereignis
Eigenschaft | Beschreibung
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auf dem Remotesystem auszuführende Postbuildereignis-Tool an.
Beschreibung | Gibt eine Beschreibung für das anzuzeigende Postbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die vom Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen remote und lokal mit der folgenden Syntax bereitgestellt werden: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2. Dabei kann eine Remotedatei an den angegebenen Speicherort auf dem lokalen Computer kopiert werden.
