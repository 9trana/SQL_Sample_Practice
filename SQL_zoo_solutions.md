
```markdown
# SQLZoo Solutions

## SQL SELECT Basics

### 1. Show the population of Germany
```sql
SELECT population FROM world
  WHERE name = 'Germany';
```

### 2. Show the name and population for 'Sweden', 'Norway', and 'Denmark'
```sql
SELECT name, population FROM world
  WHERE name IN ('Norway', 'Sweden', 'Denmark');
```

### 3. Show the country and area for countries with an area between 200,000 and 250,000
```sql
SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000;
```

## SQL SELECT from WORLD Tutorial

### 1. Show the name, continent, and population of all countries
```sql
SELECT name, continent, population FROM world;
```

### 2. Show the name for countries with a population of at least 200 million
```sql
SELECT name FROM world
  WHERE population >= 200000000;
```

### 3. Give the name and per capita GDP for countries with a population of at least 200 million
```sql
SELECT name, gdp/population FROM world 
  WHERE population >= 200000000;
```

### 4. Show the name and population in millions for South American countries
```sql
SELECT name, population/1000000 FROM world 
  WHERE continent = 'South America';
```

### 5. Show the name and population for France, Germany, and Italy
```sql
SELECT name, population FROM world 
  WHERE name IN ('France', 'Germany', 'Italy');
```

### 6. Show the countries with a name that includes 'United'
```sql
SELECT name FROM world 
  WHERE name LIKE 'UNITED%';
```

### 7. Show countries that are big by area (>3 million sq km) or population (>250 million)
```sql
SELECT name, population, area FROM world 
  WHERE area > 3000000 OR population > 250000000;
```

### 8. Show countries big by area or population but not both
```sql
SELECT name, population, area FROM world 
  WHERE area > 3000000 XOR population > 250000000;
```

### 9. Show the name, population in millions, and GDP in billions for South American countries
```sql
SELECT name, ROUND(population/1000000,2), ROUND(gdp/1000000000,2) FROM world 
  WHERE continent = 'South America';
```

### 10. Show the name and per-capita GDP for countries with a GDP of at least one trillion
```sql
SELECT name, ROUND(gdp/population/1000,0)*1000 FROM world 
  WHERE gdp > 1000000000000;
```

### 11. Show countries where the name and capital have the same number of characters
```sql
SELECT name, capital FROM world
  WHERE LENGTH(name) = LENGTH(capital);
```

### 12. Show countries where the name and capital start with the same letter
```sql
SELECT name, capital FROM world
  WHERE LEFT(name,1) = LEFT(capital,1) AND name <> capital;
```

### 13. Find the country with all vowels and no spaces in the name
```sql
SELECT name FROM world
  WHERE name LIKE '%a%'
    AND name LIKE '%e%'
    AND name LIKE '%i%'
    AND name LIKE '%o%'
    AND name LIKE '%u%'
    AND name NOT LIKE '% %';
```
```
