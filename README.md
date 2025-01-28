# PowerDNS-PTR-Template
PTR kayıtlarını hızlıca ekleyebilirsiniz.

# Örnek Kullanım 

Aşağıda olan komut 45.89.28.0/24 subneti içindir kendi subnetinize göre özelleştiriniz.

for o in {1..255}; do 
    reversed_ip=$(echo "28.89.45.$o" | awk -F. '{print $4"-"$3"-"$2"-"$1}')
    pdnsutil add-record 28.89.45.in-addr.arpa $o PTR $reversed_ip.nethiz.net
done
