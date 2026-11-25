# Razer Raiju Tournament Edition Bluetooth PIN fix

[Download the Windows x64 installer](https://github.com/Ximo-ph/raiju-te-legacy-pin-release/releases/download/v1.0.0/Raiju-TE-Legacy-PIN-Installer-v1.0.0-x64.exe)

This experimental patch is for the **Razer Raiju Tournament Edition (RZ06-02610)** with firmware **1.06.00** when Windows asks for a Bluetooth PIN and pairing fails. The controller replies with **0000** to legacy PIN requests from the PC adapter you select. The address limits which requests receive that reply. It provides no independent identity check.

**Flashing can leave the controller unable to start. Recovery after a failed flash has not been verified.** This project is independent of Razer and is provided as is, without warranty. To the extent permitted by applicable law, the authors and contributors accept no liability for device damage, loss of settings, or other loss resulting from use.

## Tested conditions

| Item | Tested |
| --- | --- |
| Controller | One Razer Raiju Tournament Edition RZ06-02610 |
| Firmware | 1.06.00 from the official Tournament Edition v1.06.00 R1 updater |
| Computer | Windows 11 x64 |
| Adapter | USB Cambridge Silicon Radio `0A12:0001`, reported as Bluetooth 2.0 + EDR |
| Result | Windows stored an authenticated bond, registered the X button wirelessly, and reconnected after power-off with one press of PS. The link remained active for more than a minute after reconnecting. |

Use this release only for that model and firmware. Compatibility with other adapters and hardware revisions remains unverified.

## Install

1. Download the official **Tournament Edition v1.06.00 R1** updater. Save the original file to use as the installer input. [Razer support](https://mysupport.razer.com/app/answers/detail/a_id/1660/kw/raiju%20tournament)
2. Download the Windows x64 helper from the release and check its SHA-256 against `SHA256SUMS.txt`. The helper is unsigned. Open it, select Razer's updater, and check that the selected Bluetooth adapter is the one you use to pair the controller.
3. Choose a new output folder, acknowledge the warning, and select **Prepare update package**. The helper validates the official download and prepares the patch locally for your adapter.
4. With the controller switched to **USB** and plugged in, select **Open Razer updater**. Check that the device shows **1.06.00** and the target label is **1.06.01**. Click **Update** once. Keep the PC powered and the cable connected through writing and verification.
5. Close the updater once the controller returns to normal USB mode. The controller still reports **1.06.00**, and **1.06.01** is a package label that enables the write. This can make the button appear again after completion.
6. Disconnect USB, switch to **PC BT**, and hold **OPTIONS + PS** until the light flashes rapidly. Select the Raiju in Windows Bluetooth settings and enter **0000** when asked. If an earlier failed entry blocks discovery, remove that Raiju entry and pair it again.
7. Test the X button wirelessly. Power the controller off and press **PS** once to check that it reconnects with the saved bond.

The release contains the compiled helper and a separate description of the binary patch. The original Razer updater is obtained from Razer, and the complete firmware image is generated locally. [Release files and checksums](https://github.com/Ximo-ph/raiju-te-legacy-pin-release/releases/tag/v1.0.0)

## Resumen en español

Parche experimental para el **Raiju Tournament Edition RZ06-02610 con firmware 1.06.00**. El instalador de Windows pide el actualizador oficial de Razer y prepara una copia para el adaptador Bluetooth de tu PC. Si Windows pide PIN, introduce **0000**.

Lo probamos en un mando con Windows 11 y un adaptador USB Bluetooth 2.0 + EDR. Verificamos las pulsaciones por Bluetooth y la reconexión al pulsar **PS** tras apagar el mando. **Si falla la grabación, el mando puede dejar de arrancar. No hemos comprobado una vía de recuperación.** Se ofrece tal cual, sin garantía y sin responsabilidad por daños o pérdidas en la medida permitida por la ley.

En el actualizador pulsa **Actualizar** una sola vez y mantén el cable conectado hasta que termine. **1.06.01** es la etiqueta del paquete. Es normal que el mando siga indicando **1.06.00** y que la ventana vuelva a ofrecer la actualización. Cierra el actualizador después del primer ciclo completo.
