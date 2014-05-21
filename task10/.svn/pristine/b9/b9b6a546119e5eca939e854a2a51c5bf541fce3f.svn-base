package com.qunar;

import java.util.Calendar;
import java.util.Date;

/**
 * Created by shaotianma on 14-5-9.
 */
public class MyDateUtil {
    public static Calendar TOOLCAL = Calendar.getInstance();
    private MyDateUtil() {
        throw new IllegalArgumentException();
    }

    /**
     * 得到当前天的下一天
     * @param today
     * @return
     */
    public static MyDate nextDay(MyDate today) {
        TOOLCAL.set(Calendar.YEAR, today.getYear());
        TOOLCAL.set(Calendar.MONTH, today.getMonth() - 1);
        TOOLCAL.set(Calendar.DAY_OF_MONTH, today.getDay());

        long lToday = TOOLCAL.getTimeInMillis();
        long lNextDay = lToday + 24 * 60 * 60 * 1000;

        TOOLCAL.setTimeInMillis(lNextDay);

        int year = TOOLCAL.get(Calendar.YEAR);
        int month = TOOLCAL.get(Calendar.MONTH) + 1;
        int day = TOOLCAL.get(Calendar.DAY_OF_MONTH);

        return new MyDate(year, month, day);
    }

    /**
     * 把一个形如“2014-05-09”变成一个MyDate对象
     * @param date
     * @return
     */
    public static MyDate stringToMyDate(String date) {
        int firstIndex = date.indexOf("-");
        int secondIndex = date.indexOf("-", firstIndex + 1);

        if(firstIndex == -1 || secondIndex == -1) throw new IllegalArgumentException("日期字符不对");

        int year = Integer.parseInt(date.substring(0,firstIndex));
        int month = Integer.parseInt(date.substring(firstIndex + 1, secondIndex));
        int day = Integer.parseInt(date.substring(secondIndex + 1));

        return new MyDate(year, month, day);
    }
}
