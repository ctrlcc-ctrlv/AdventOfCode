import re

with open("input day 4.txt") as file:
    data = file.read().split("\n\n")

compulsory_keys = ['byr', 'iyr', 'eyr', 'hgt', 'hcl', 'ecl', 'pid']
part1, part2 = 0, 0


for passport in data:
        row = re.sub(r'[\n ]{1,}', ", ", passport) + ","
        d = dict(re.findall(r'([a-z]+):(.*?),', row))
        ecl= ["amb", "blu", "brn", "gry", "grn", "hzl", "oth"]

        if all([key in d.keys() for key in compulsory_keys]):
            part1 += 1

            if (1920 <= int(d['byr']) <= 2002 and
                2010 <= int(d['iyr']) <= 2020 and
                2020 <= int(d['eyr']) <= 2030 and
                d['ecl'] in ecl and
                re.search(r'^#[0-9a-f]{6}$', d['hcl']) and
                re.match('^\d{9}$', d['pid'])):

                height = d['hgt']
                if (height[-2:] == 'cm' and 150 <= int(height[:-2]) <= 193) or (height[-2:] == 'in' and 59 <= int(height[:-2]) <= 76):
                    part2 += 1
print('%d valid passports for part 1' % part1)
print('%d valid passports for part 2' % part2)
