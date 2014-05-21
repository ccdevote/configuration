package com.qunar;

import com.google.common.collect.ComparisonChain;

/**
 * Created by shaotianma on 14-5-9.
 */
public class MyDate implements Comparable<MyDate>{
    public final int year;
    public final int month;
    public final int day;

    public MyDate(int year, int month, int day) {
        this.year = year;
        this.month = month;
        this.day = day;
    }

    public int getYear() {
        return year;
    }

    public int getMonth() {
        return month;
    }

    public int getDay() {
        return day;
    }

    //重写
    @Override public String toString() {
        return year + "-" + formatNumber(month) + "-" + formatNumber(day);
    }
    //硬编码了
    private String formatNumber(int i) {
        return i <= 9 ? "0" + i : "" +i;
    }
    //为了去重
    @Override public int hashCode() {
        return year + month + day;
    }
    //重写了equals方法
    @Override public boolean equals(Object obj) {
        if(!(obj instanceof MyDate)) return false;
        MyDate date = (MyDate)obj;
        if(this.getYear() == date.getYear() && this.getMonth() == date.getMonth() && this.getDay() == date.getDay())
            return true;
        return false;
    }
    //方便使用equals方法
    @Override public int compareTo(MyDate date) {
        return ComparisonChain.start()
                .compare(this.getYear(), date.getYear())
                .compare(this.getMonth(), date.getMonth())
                .compare(this.getDay(), date.getDay())
                .result();

    }

}
