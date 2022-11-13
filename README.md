# Formula1-Database-Project






# Nav's part, bottom part of our UoD


CREATE TABLE `constructorResults` (
  `constructorResultsId` int(11) NOT NULL AUTO_INCREMENT,
  `pointsGained` float DEFAULT NULL,
  `raceId` int(11) NOT NULL DEFAULT '0',
  `constructorId` int(11) NOT NULL DEFAULT '0',
  PRIMARY KEY (`constructorResultsId`)
);

-- Add timing composite key with attr (secs, min, millisecs)
CREATE TABLE `lapTimes` (
  `driverId` int(11) NOT NULL,
  `lapTimeId` int(11) NOT NULL,
  `raceId` int(11) NOT NULL,
  `lap` int(11) NOT NULL,
  `position` int(11) DEFAULT NULL,
  PRIMARY KEY (`raceId`,`driverId`,`lap`),
  KEY `raceId` (`driverId`)
);



CREATE TABLE `qualifying` (
  `qualiId` int(11) NOT NULL AUTO_INCREMENT,
  `raceId` int(11) NOT NULL DEFAULT '0',
  `driverCode` int(11) NOT NULL DEFAULT '0',
  `constructorId` int(11) NOT NULL DEFAULT '0',
  `number` int(11) NOT NULL DEFAULT '0',
  `position` int(11) DEFAULT NULL,
  `driverNumber` int(11) DEFAULT NULL,
  PRIMARY KEY (`qualiId`)
)

-- add time mulitvalued with disjoint (qualiTime, raceTime)
-- add date multivalued with disjoint (qualiDate, raceDate)  
CREATE TABLE `races` (
  `raceId` int(11) NOT NULL AUTO_INCREMENT,
  `round` int(11) NOT NULL DEFAULT '0',
  `circuitId` int(11) NOT NULL DEFAULT '0',
  PRIMARY KEY (`raceId`),
);

-- add timing composite key with attr (secs, min, millisecs)
CREATE TABLE `results` (
  `resultId` int(11) NOT NULL AUTO_INCREMENT,
  `raceId` int(11) NOT NULL DEFAULT '0',
  `constructorId` int(11) NOT NULL DEFAULT '0',
  `driverNumber` int(11) DEFAULT NULL,
  `laps` int(11) NOT NULL DEFAULT '0',
  `fastestLap` varchar(255) DEFAULT NULL,
  `fastestLapTime` varchar(255) DEFAULT NULL,
  `grid` int(11) NOT NULL DEFAULT '0',
  `points` float NOT NULL DEFAULT '0',
  `driverId` int(11) NOT NULL DEFAULT '0',
  `driverCode` int(11) NOT NULL DEFAULT '0',
  PRIMARY KEY (`resultId`)
)


-- add timing composite key with attr (minutes, seconds, millisecs)
CREATE TABLE `sprintResults` (
  `sprintResultId` int(11) NOT NULL AUTO_INCREMENT,
  `raceId` int(11) NOT NULL DEFAULT '0',
  `driverId` int(11) NOT NULL DEFAULT '0',
  `constructorId` int(11) NOT NULL DEFAULT '0',
  `number` int(11) NOT NULL DEFAULT '0',
  `points` float NOT NULL DEFAULT '0',
  `driverCode` int(11) NOT NULL DEFAULT '0',
  `grid` int(11) NOT NULL DEFAULT '0',
  `position` int(11) DEFAULT NULL,
  `fastestLap` varchar(255) DEFAULT NULL,
  `fastestLapTime` varchar(255) DEFAULT NULL,
  `positionOrder` int(11) NOT NULL DEFAULT '0',
  `laps` int(11) NOT NULL DEFAULT '0',
  PRIMARY KEY (`sprintResultId`),
  KEY `raceId` (`raceId`)
);


CREATE TABLE `tireCompounds` (
  `tireId` int(11) NOT NULL AUTO_INCREMENT,
  `hards` varchar(255) NOT NULL DEFAULT '0',
  `mediums` varchar(255) NOT NULL DEFAULT '0',
  `softs` varchar(255) NOT NULL DEFAULT '0',
  `inters` varchar(255) NOT NULL DEFAULT '0',
  `wets` varchar(255) NOT NULL DEFAULT '0',
  PRIMARY KEY (`statusId`)
) ;
