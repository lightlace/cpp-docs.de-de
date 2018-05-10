---
title: Remotebuildereignisse (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 165d3690-5bd8-4b0b-bc66-8b699d85a61b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 38c036bf747115823b853d0d66077f4402a7f7ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="build-event-properties-linux-c"></a>Buildereigniseigenschaften (Linux C++) 

## <a name="pre-build-event"></a>Präbuildereignis

Eigenschaft | description
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auszuführende Präbuildereignis-Tool an.
description | Gibt eine Beschreibung für das anzuzeigende Präbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.

## <a name="pre-link-event"></a>Prälinkereignis

Eigenschaft | description
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auszuführende Prälinkereignis-Tool an.
description | Gibt eine Beschreibung für das anzuzeigende Prälinkereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.

## <a name="post-build-event"></a>Postbuildereignis

Eigenschaft | description
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auszuführende Postbuildereignis-Tool an.
description | Gibt eine Beschreibung für das anzuzeigende Postbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.

## <a name="remote-pre-build-event"></a>Remote-Präbuildereignis

Eigenschaft | description
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auf dem Remotesystem auszuführende Präbuildereignis-Tool an.
description | Gibt eine Beschreibung für das anzuzeigende Präbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die vom Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen remote und lokal mit der folgenden Syntax bereitgestellt werden: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2. Dabei kann eine Remotedatei an den angegebenen Speicherort auf dem lokalen Computer kopiert werden.

## <a name="remote-pre-link-event"></a>Remote-Prälinkereignis

Eigenschaft | description
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auf dem Remotesystem auszuführende Prälinkereignis-Tool an.
description | Gibt eine Beschreibung für das anzuzeigende Prälinkereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die vom Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen remote und lokal mit der folgenden Syntax bereitgestellt werden: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2. Dabei kann eine Remotedatei an den angegebenen Speicherort auf dem lokalen Computer kopiert werden.

## <a name="remote-post-build-event"></a>Remote-Postbuildereignis

Eigenschaft | description
--- | ---
Befehlszeile | Gibt eine Befehlszeile für das auf dem Remotesystem auszuführende Postbuildereignis-Tool an.
description | Gibt eine Beschreibung für das anzuzeigende Postbuildereignis-Tool an.
In Build verwenden | Gibt an, ob dieses Buildereignis aus dem Build für die aktuelle Konfiguration ausgeschlossen wird.
Zusätzliche zu kopierende Dateien | Gibt zusätzliche Dateien an, die vom Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen remote und lokal mit der folgenden Syntax bereitgestellt werden: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2. Dabei kann eine Remotedatei an den angegebenen Speicherort auf dem lokalen Computer kopiert werden.
