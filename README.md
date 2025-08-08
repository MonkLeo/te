# te
{
  "inbounds" : [
    {
      "listen" : "127.0.0.1",
      "port" : 1080,
      "protocol" : "socks",
      "settings" : {
        "auth" : "noauth",
        "udp" : true
      },
      "sniffing" : {
        "destOverride" : [
          "http",
          "tls",
          "quic",
          "fakedns"
        ],
        "enabled" : false,
        "routeOnly" : true
      },
      "tag" : "socks"
    }
  ],
  "outbounds" : [
    {
      "protocol" : "vless",
      "settings" : {
        "vnext" : [
          {
            "address" : "80.78.31.211",
            "port" : 443,
            "users" : [
              {
                "encryption" : "none",
                "flow" : "xtls-rprx-vision",
                "id" : "de28e6c4-f4e3-4a30-9e73-c26be4e28bd8"
              }
            ]
          }
        ]
      },
      "streamSettings" : {
        "network" : "tcp",
        "realitySettings" : {
          "fingerprint" : "firefox",
          "publicKey" : "i2m35RncSX7X1_d_abkQHQWANUHLzhg6MIfNHKKD6lY",
          "serverName" : "vk.com",
          "shortId" : "ffffffffff"
        },
        "security" : "reality",
        "tcpSettings" : {
          "header" : {
            "request" : {
              "headers" : {

              }
            },
            "type" : "none"
          }
        }
      },
      "tag" : "proxy"
    },
    {
      "protocol" : "freedom",
      "tag" : "direct"
    },
    {
      "protocol" : "blackhole",
      "tag" : "block"
    }
  ]
}
