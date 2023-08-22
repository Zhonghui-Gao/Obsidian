芯片：RTL8211F-CG

drivers/net/ethernet/stmicro/stmmac/dwmac-rk.c

6.4__rockchip64__arm64/drivers/net/ethernet/realtek

lan0:GMAC0_INT/PMEB_GPIO2_D2
lan1:GMAC1_INT/PMEB_GPIO2_D0

GPIO端口号

``` SHELL
aliases {
		ethernet0 = &gmac0;
		ethernet1 = &gmac1;
		mmc0 = &sdmmc0;
		mmc1 = &sdhci;
	};
```


```SHELL
&gmac0 {
	snps,reset-gpio = <&gpio2 RK_PD2 GPIO_ACTIVE_LOW>;
	snps,reset-active-low;
	/* Reset time is 20ms, 100ms for rtl8211f */
	snps,reset-delays-us = <0 20000 100000>;

	assigned-clocks = <&cru SCLK_GMAC1_RX_TX>, <&cru SCLK_GMAC1>;
	assigned-clock-parents = <&cru SCLK_GMAC1_RGMII_SPEED>, <&gmac1_clkin>;
	clock_in_out = "input";
	phy-handle = <&rgmii_phy0>;
	phy-mode = "rgmii";

	pinctrl-names = "default";
	pinctrl-0 = <&gmac1m1_miim
		     &gmac1m1_tx_bus2
		     &gmac1m1_rx_bus2
		     &gmac1m1_rgmii_clk
		     &gmac1m1_rgmii_bus
		     &gmac1m1_clkinout>;

	tx_delay = <0x4f>;
	rx_delay = <0x26>;

	status = "okay";
};
```

```SHELL
&gmac1 {
	snps,reset-gpio = <&gpio2 RK_PD0 GPIO_ACTIVE_LOW>;
	snps,reset-active-low;
	/* Reset time is 20ms, 100ms for rtl8211f */
	snps,reset-delays-us = <0 20000 100000>;

	assigned-clocks = <&cru SCLK_GMAC1_RX_TX>, <&cru SCLK_GMAC1>;
	assigned-clock-parents = <&cru SCLK_GMAC1_RGMII_SPEED>, <&gmac1_clkin>;
	clock_in_out = "input";
	phy-handle = <&rgmii_phy1>;
	phy-mode = "rgmii";

	pinctrl-names = "default";
	pinctrl-0 = <&gmac1m1_miim
		     &gmac1m1_tx_bus2
		     &gmac1m1_rx_bus2
		     &gmac1m1_rgmii_clk
		     &gmac1m1_rgmii_bus
		     &gmac1m1_clkinout>;

	tx_delay = <0x4f>;
	rx_delay = <0x26>;

	status = "okay";
};
```

```
&mdio1 {
	rgmii_phy1: ethernet-phy@0 {
		compatible = "ethernet-phy-ieee802.3-c22";
		reg = <0x0>;
	};
};
```