# Victimization in DDoS Attacks: The Role of Popularity and Industry Sector

There are three datasets:
- `attack_data.csv`: Consists of all DDoS attempts that target a single entity, e.g., not a shared IP address.
- `all_targets_data.csv`: The list of unique targeted IP addresses based on attack_data.csv.
- `top100k_data.csv`: Infrastructure data of all top 100K most popular websites based on Alexa rank, regardless being targeted or not.

## Anonymization
For privacy purposes, all information enabling the discovery of the actual targets is undisclosed or has been anonymized.

## `attack_data.csv`
- `target_hash`: hashed IP address of the target
- `attack_data`: the date of DDoS attempt recorded by the network telescope
- `is_outlier`: indicator of whether the attack is flagged as an outlier in our study, e.g., if attack_date == "2017-02-25" or domain == "guff.com"

## `all_targets_data.csv`
- `target_hash`: hashed IP address of the target
- `rank_bin_upper`: the upper limit of the thousand-ranged bin (i.e., each bin has a range of 1000) that the target popularity rank falls into, e.g., if the rank is 1234 then the rank_bin_upper is 2000. If the target rank is above 1 million, then the rank_bin_upper value is 999999999.

## `top100k_data.csv`
- `target_hash`: hashed IP address of the top 100k domain infrastructure
- `rank_bin_upper`: upper limit of the thousand-ranged bin (i.e., each bin has a range of 1000) that the target popularity rank falls into, e.g., if the rank is 1234 then the rank_bin_upper is 2000. If the target rank is above 1 million, then the rank_bin_upper value is 999999999.
- `dc_datacenter`: name of the IP address datacenter. NOT_DC means that the IP address is not in a datacenter.
- `dc_domain`: domain name address of the IP address datacenter company. NOT_DC means that the IP address is not in a datacenter.
- `dc_provider`: datacenter provider label given from the clustering process of the datacenters from the same provider based on the name and the domain name address.
- `tag`: content category tags given by Cisco Umbrella for the domain name. One domain name can have multiple tags. Unknown() means that the category of the domain name is unknown.
