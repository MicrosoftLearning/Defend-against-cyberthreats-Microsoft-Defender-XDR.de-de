---
lab:
  title: Konfigurieren von Microsoft Defender
  module: Configure the Microsoft Defender XDR environment
---
Sie arbeiten als Security Operations Analyst in einem Unternehmen, das Microsoft Defender XDR implementiert. Ihre Rolle besteht darin, das IT-Team des Unternehmens dabei zu unterstützen, sich gegen Bedrohungen mit Microsoft Defender (XDR) zu verteidigen. Der Unternehmensführung ist es sehr wichtig, dass alle Richtlinien und Anforderungen eingehalten werden, wenn Sie die notwendigen Schritte in der Azure-Umgebung des Unternehmens durchführen.

# Konfigurieren der Microsoft Defender XDR-Umgebung

In dieser Übung stellen Sie Ihre Microsoft Defender XDR-Umgebung bereit, integrieren Clientarbeitsstationen in Defender for Endpoint und führen ein simuliertes Angriffsszenario auf einer Clientarbeitsstation aus.

Diese Übung dauert ca. **10-15** Minuten.

>**Wichtig:** Sie benötigen Zugriff auf einen Microsoft 365 E5-Mandanten mit einer P2-Lizenz für Microsoft Defender for Endpoint, um die folgenden Übungen durchzuführen. Außerdem müssen Sie über Microsoft Windows 10- oder 11-Clientarbeitsstationen verfügen, um simulierte Angriffe zu integrieren und auszuführen.

## Aufgabe 1: Vorbereiten des Microsoft Defender XDR-Arbeitsbereichs

1. Wechseln Sie im Microsoft Edge-Browser zum Microsoft Defender-Portal unter (<https://security.microsoft.com>).
1. Wählen Sie im **Microsoft Defender**-Portal im Navigationsmenü auf der linken Seite **Startseite** aus.

    >**Hinweis:** Möglicherweise müssen Sie im Menü ganz nach oben scrollen.

1. Scrollen Sie die Menüelemente nach unten zu **Ressourcen**, und wählen Sie **Geräte** aus.

1. Der Prozess zum Bereitstellen des Defender XDR-Arbeitsbereichs sollte gestartet werden, und es sollten Meldungen wie *Laden und Initialisieren* kurz oben auf der Seite angezeigt werden. Dann sehen Sie ein Bild eines Kaffeebechers und folgende Meldung: **Warten Sie einen Moment! Wir bereiten neue Orte für Ihre Daten vor und verbinden sie.** Die Bereitstellung dauert ungefähr fünf Minuten. *Lassen Sie die Seite geöffnet, und stellen Sie sicher, dass die Bereitstellung abgeschlossen wird, da sie für das nächste Lab erforderlich ist.*

    >**Hinweis:** Ignorieren Sie die Popups mit der Fehlermeldung: *Einige Ihrer Daten können nicht abgerufen werden*. Wenn die Meldung „Warten Sie einen Moment. Wir bereiten neue Speicherplätze für Ihre Daten vor und verknüpfen sie.“ nicht angezeigt wird, oder die Seite „Einstellungen > Microsoft Defender XDR > Konto“ geöffnet wird, Ihnen jedoch die Meldung *Fehler beim Laden des Datenspeicherorts. Versuchen Sie es später erneut.* angezeigt wird, wählen Sie im Menü „Allgemein“ die Option „Diensteinstellungen für Warnungen“ aus.

1. Wenn die neue Arbeitsbereichsinitialisierung erfolgreich abgeschlossen ist, wird auf der Portalseite **Startseite** ein Banner **SIEM und XDR an einem zentralen Ort abrufen** angezeigt. Außerdem sind in den **Einstellungen** die allgemeinen Microsoft Defender XDR-Einstellungen für Konto, E-Mail-Benachrichtigungen, **Vorschaufeatures**, Warnungsdiensteinstellungen, Berechtigungen und Rollen und Streaming-API jetzt aktiviert.

### Aufgabe 2: Anwenden der voreingestellten Sicherheitsrichtlinien von Microsoft Defender für Office 365

In dieser Aufgabe weisen Sie im Microsoft 365 Security-Portal voreingestellte Sicherheitsrichtlinien für Exchange Online Protection (EOP) und Microsoft Defender for Office 365 zu.

1. Melden Sie sich beim virtuellen Computer WIN1 als Administrator mit dem Kennwort **Pa55w.rd** an.  

1. Starten Sie den Microsoft Edge-Browser.

1. Wechseln Sie im Microsoft Edge-Browser zum Microsoft Defender XDR-Portal unter <https://security.microsoft.com>.

1. Kopieren Sie im Dialogfeld **Anmelden**das von Ihrem Labhostinganbieter bereitgestellte Mandanten-E-Mail-Konto für den Administrator, und fügen Sie es ein, und wählen Sie dann **Weiter** aus.

1. Kopieren Sie im Dialogfeld **Kennwort eingeben** das von Ihrem Labhostinganbieter bereitgestellte Mandantenkennwort für den Administrator, und fügen Sie es ein, und wählen Sie dann **Anmelden** aus.

    >**Hinweis:** Wenn Sie die Meldung „Der Vorgang konnte nicht abgeschlossen werden. Versuchen Sie es später noch mal. Wenn das Problem weiterhin besteht, wenden Sie sich an den Microsoft-Support.“ Klicken Sie einfach auf **OK**, um fortzufahren.  

1. Wenn angezeigt, schließen Sie das Popupfenster der Microsoft Defender XDR-Schnelltour. **Hinweis:** Zu einem späteren Zeitpunkt in diesem Lab müssen Sie warten, bis der Defender-Arbeitsbereich bereitgestellt wird. Sie können diese Zeit nutzen, um durch die geführten Touren zu navigieren und mehr über Microsoft Defender XDR zu erfahren.

1. Wählen Sie im Navigationsmenü unter *E-Mail & Zusammenarbeit* den Bereich **Richtlinien und Regeln** aus.

1. Wählen Sie im Dashboard *Richtlinien und Regeln*die Option **Bedrohungsrichtlinien**aus.

1. Wählen Sie im Dashboard *Bedrohungsrichtlinien* die Option **Voreingestellte Sicherheitsrichtlinien** aus.

    >**Hinweis:** Wenn Sie die Meldung *„Client Fehler – Fehler beim Abrufen der BIP-Regel“* erhalten, wählen Sie **OK** aus, um fortzufahren. Der Fehler ist auf den Hydrationsstatus Ihres Mandanten in Office 365 zurückzuführen, der standardmäßig nicht aktiviert ist.

    >**Hinweis:** Wenn Sie die Meldung erhalten: *„Client-Fehler – Beim Abrufen der voreingestellten Sicherheitsrichtlinien ist ein Fehler aufgetreten. Bitte versuchen Sie es später erneut.“* Wählen Sie **OK** aus, um fortzufahren. Aktualisieren Sie Ihren Browser mit **STRG+F5**.

1. Wählen Sie auf der Seite **Erfahren Sie mehr über die voreingestellten Sicherheitsrichtlinien***Aufklappen* **Schließen** aus.

1. Wählen Sie unter *Standardschutz* die Option **Schutzeinstellungen verwalten** aus. **Hinweis:** Wenn diese Option grau dargestellt wird, aktualisieren Sie Ihren Browser mit **Strg+F5**.

1. Wählen Sie im Abschnitt *Exchange Online Protection anwenden* die Option **Bestimmte Empfänger** und beginnen Sie unter **Domänen** mit der Eingabe des Domänennamens Ihres Mandanten, wählen Sie ihn aus und wählen Sie dann **Weiter**aus.

    >**Hinweis:** Der Domänenname Ihres Mandanten ist derselbe Name wie der Ihres Administratorkontos. Dieser könnte *WWLx######.onmicrosoft.com* lauten. Beachten Sie, dass diese Konfiguration Richtlinien für Anti-Spam, ausgehenden Spam, Anti-Malware und Anti-Phishing anwendet.

1. Wenden Sie im Abschnitt *Defender for Office 365-Schutz anwenden* die gleiche Konfiguration wie im vorherigen Schritt an und wählen Sie **Weiter**aus. Beachten Sie, dass diese Konfiguration Richtlinien für Anti-Phishing, sichere Anhänge und sichere Links anwendet.

1. Wählen Sie im Abschnitt *Schutz vor Identitätswechsel* viermal (4x) **Weiter**aus, um fortzufahren.

1. Vergewissern Sie sich im Abschnitt *Richtlinienmodus*, dass die Optionsschaltfläche **Richtlinie nach Abschluss aktivieren** aktiviert ist, und wählen Sie dann **Weiter**aus.

1. Lesen Sie den Inhalt unter *Änderungen überprüfen und bestätigen* und wählen Sie **Bestätigen**aus, um die Änderungen zu übernehmen und wählen Sie **Fertig**aus, um den Vorgang abzuschließen.

    >**Hinweis:** Wenn Sie die Meldung *„Der URI ‚<https://outlook.office365.com/psws/service.svc/AntiPhishPolicy>‘ ist für die PUT-Operation nicht gültig. Der URI muss auf eine einzelne Ressource für PUT-Operationen zeigen“*, wählen Sie einfach **OK** und dann **Abbrechen**, um zur Hauptseite zurückzukehren. Sie werden sehen, dass die Option *Standardschutz ist aktiviert* aktiviert ist.

1. Wählen Sie unter *Strenger Schutz* die Option **Schutzeinstellungen verwalten**aus. **Hinweis: ***Strenger Schutz* finden Sie unter „E-Mails und Zusammenarbeit – Richtlinien und Regeln – Bedrohungsrichtlinien – Voreingestellte Sicherheitsrichtlinien“.

1. Wählen Sie unter *Exchange Online Protection anwenden* die Option **Bestimmte Empfänger** und beginnen Sie unter **Gruppen** mit der Eingabe von **Führung**, wählen Sie diese aus und wählen Sie dann **Weiter**aus. Beachten Sie, dass diese Konfiguration Richtlinien für Anti-Spam, ausgehenden Spam, Anti-Malware und Anti-Phishing anwendet.

1. Wenden Sie im Abschnitt *Defender for Office 365-Schutz anwenden* die gleiche Konfiguration wie im vorherigen Schritt an und wählen Sie **Weiter**aus. Beachten Sie, dass diese Konfiguration Richtlinien für Anti-Phishing, sichere Anhänge und sichere Links anwendet.

1. Wählen Sie im Abschnitt *Schutz vor Identitätswechsel* viermal (4x) **Weiter**aus, um fortzufahren.

1. Vergewissern Sie sich im Abschnitt *Richtlinienmodus*, dass die Optionsschaltfläche **Richtlinie nach Abschluss aktivieren** aktiviert ist, und wählen Sie dann **Weiter**aus.

1. Lesen Sie den Inhalt unter *Änderungen überprüfen und bestätigen* und wählen Sie **Bestätigen**aus, um die Änderungen zu übernehmen und wählen Sie **Fertig**aus, um den Vorgang abzuschließen.

    >**Hinweis:** Wenn Sie die Meldung *„Der URI ‚<https://outlook.office365.com/psws/service.svc/AntiPhishPolicy>‘ ist für die PUT-Operation nicht gültig. Der URI muss auf eine einzelne Ressource für PUT-Operationen zeigen“*, wählen Sie einfach **OK** und dann **Abbrechen**, um zur Hauptseite zurückzukehren. Sie werden sehen, dass die Option *Strenger Schutz ist aktiviert* aktiviert ist.

## Damit haben Sie das Lab beendet
